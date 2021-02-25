<template>
  <button :type="type" :class="mode">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: ['type', 'mode']
};
</script>

<style scoped>
button {
  padding: 0.75rem 1.5rem;
  font-family: inherit;
  background-color: #42b983;
  border: 0px;
  color: white;
  cursor: pointer;
  outline: none;
}

button:hover,
button:active {
  background-color: #5fbd93;
  border-color: #5fbd93;
}

.flat {
  background-color: transparent;
  color: #42b983;
  border: none;
}

.flat:hover,
.flat:active {
  background-color: #5fbd93;
  color: white;
}

.delete {
  background-color: transparent;
  color: #42b983;
  border: none;
}
.delete:hover,
.delete:active {
  border-radius: 10px;
  background-color: #ed5e68;
  color: white;
}
</style>
