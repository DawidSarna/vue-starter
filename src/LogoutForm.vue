<template>
   <div>
	<h3>Witaj {{ email }}</h3>
	<button @click="logout()">Wyloguj</button>
   </div>
</template>

<script>
export default {
 props: ['email'],

 data() {
     return {
         email: '',
     }
 },
 methods: {
  logout() {
  this.$emit('logout');
  }
 }
}
</script>