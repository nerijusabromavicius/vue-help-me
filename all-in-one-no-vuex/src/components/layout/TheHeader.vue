<template>
  <header>
    <h3>{{ title }}</h3>
  </header>
</template>

<script>
export default {
  props: ['title']
};
</script>

<style scoped>
header {
  width: 100%;
  height: 3rem;
  background-color: #42b983;
  display: flex;
  justify-content: center;
  align-items: center;
}

header h3 {
  color: white;
  margin: 0;
}
</style>
