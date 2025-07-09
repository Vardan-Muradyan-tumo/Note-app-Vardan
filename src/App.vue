<script setup>
import Card from './components/card.vue'

</script>

<template>
 

<main class="main">
<h1>Note App</h1>
<div class="notes">
  <Card/>
</div>
</main>
</template>

<style >
body,
#app{
  width: 100%;
  min-height: 100%;
  color: black;
}
main.main{
  background: linear-gradient(128deg, rgba(135, 246, 180, 0.84) 12.75%, rgba(50, 180, 187, 0.67) 83.4%);

    width: 100%;
  min-height: 100vh;
}
h1{
  font-family: Inter;
font-weight: 700;
font-style: Bold;
font-size: 32px;
line-height: 100%;
letter-spacing: 0%;
text-align: center;
}
</style>
