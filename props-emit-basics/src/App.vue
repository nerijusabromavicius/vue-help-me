<template>
<div>
  <active-user :users="users"></active-user>
  <user-data @send-user-data="setUserData"></user-data>
</div>  
</template>

<script>
 export default {
   data() {
     return {
       users: [
         {
           name: "Nerijus",
           age: "69"
         },
         {
           name: "Nerijus",
           age: "69"
         },
         {
           name: "Nerijus",
           age: "69"
         },
         {
           name: "Nerijus",
           age: "69"
         },
         {
           name: "Nerijus",
           age: "69"
         }
       ]
     }
   },
   methods: {
     setUserData(user) {
       console.log(user)
       this.users.push(user)
     }
   }
 }
</script>
