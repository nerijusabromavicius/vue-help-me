<template>
  <div>
    <div v-for="user in users" :key="user.id">
      <h2>User Name: {{user.name}}</h2>
      <h3>Age: {{user.age}} </h3>
    </div>
  </div>
</template>

<script>
  export default {
    props: {users: {name: "", age: ""}},
    data() {
      return this.users
    }
  };
</script>
