<script setup>
import Card from './components/card.vue'
import Add_button from './components/Add_button.vue'
import AddNewNote from './components/AddNewNote.vue'
import { ref, onMounted , computed} from 'vue'
import search from './components/search.vue'

const isVisible = ref(false)
const notes = ref([])
const word = ref('')

function onSearch(value){
  word.value = value
}

function addNote(title, content) {
  let note = {
    title: title,
    content: content,
    time: (new Date()).toLocaleDateString()
  }
  notes.value.push(note);
  isVisible.value = false
  localStorage.setItem('notes', JSON.stringify(notes.value))
}


const togglePopup = () => {
  isVisible.value = !isVisible.value
}

const removeNote = (index) => {
  notes.value.splice(index, 1)
  localStorage.setItem('notes', JSON.stringify(notes.value))
}

onMounted(function () {
  let saveNotes = localStorage.getItem('notes')
  if (saveNotes) {
    let obj = JSON.parse(saveNotes)
    notes.value = obj
    
  }

})
const filteredNotes= computed(() => notes.value.filter(
  (item)=>item.title.includes(word.value)
))
</script>

<template>


  <main class="main">
    <div class="header">
      <h1>Note App</h1>
      <search @onSearch="onSearch"/>
    </div>

    <div class="notes">
      <Card v-for="(item, index) in filteredNotes" :title="item.title" :content="item.content" :time="item.time"
        @onDelete="removeNote(index)" />

    </div>
    <Add_button @click="togglePopup" />
    <AddNewNote v-if="isVisible" @onClose="togglePopup" @onSave="addNote" />

  </main>
</template>

<style>
body,
#app {
  width: 100%;
  min-height: 100%;
  color: black;
}

main.main {
  background: linear-gradient(128deg, rgba(135, 246, 180, 0.84) 12.75%, rgba(50, 180, 187, 0.67) 83.4%);

  width: 100%;
  min-height: 100vh;
  padding: 24px;

}

h1 {
  font-family: Inter;
  font-weight: 700;
  font-style: Bold;
  font-size: 32px;
  line-height: 100%;
  letter-spacing: 0%;
  text-align: center;
  margin-bottom: 50px;
}

.notes {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  gap: 26px;
  flex-wrap: wrap;
  justify-content: center;

}

.header {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-around;
}
</style>
