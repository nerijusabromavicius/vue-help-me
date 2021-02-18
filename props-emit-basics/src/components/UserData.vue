<template>
    <div>
      <form @submit.prevent="addUser()">
        <label>Name</label>
        <input type="text" name="name" v-model="name" />
        <label>Age</label>
        <input type="text" name="age" v-model="age"/>  
        <button type="submit">Add user</button>
      </form>
    </div>
</template>

<script>
  export default {
    emits: ['send-user-data'],
    data() {
      return{
        name: "",
        age: ""
      }
    },
    methods: {
      addUser() {
        const newUser = {name: this.name, age: this.age}
        console.log(newUser)
        this.$emit('send-user-data', newUser)
      }

    }
  };
</script>

