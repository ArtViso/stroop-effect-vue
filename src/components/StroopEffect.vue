<template>
  <header>
    <img alt="Vue logo" style="width:50px; height:50px" src="../assets/logo.png">
    <h1>Stroop effect</h1>
  </header>
  <section>
    <div class="box">
      <template v-for="item in objects">
        <span v-for="(key, value) in item" :style="{color: key}">
          {{ value.toUpperCase() }}
        </span>
      </template>
    </div>
  </section>
</template>

<script setup lang="ts">

const words = ['red', 'blue', 'black', 'yellow', 'white', 'pink', 'orange', 'grey'];
const colors = ['red', 'blue', 'black', 'yellow', 'white'];
const objects = [];

const randomElement = (elements: any) => {
  return elements[Math.floor(Math.random() * elements.length)]
}

function createObject() {
  const keyWord = randomElement(words);
  const valueColor = randomElement(colors.filter(color => color !== keyWord));
  let obj: Record<string, unknown> = {
    [keyWord] : valueColor
  };
  return obj
}

for (let i = 0; i < 50; i++) {
  objects.push({...createObject()})
}

</script>
<style scoped>
.box {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
  padding: 2.5rem;
  width: 400px;
  margin: auto;
  flex-wrap: wrap;
  background: #C4C4C4;
}
</style>

