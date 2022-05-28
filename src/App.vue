<template>
  <div>
  
<h1>Twój e-mail to: {{ email }}</h1>
<div v-if="email.length == 0">podaj swoj e-mail</div>
<div v-else-if="email.length < 10 & email.length > 0">Ale masz krótki adres!</div>
<div v-else-if="email.length < 20">Twój adres e-mail jest w sam raz.</div>
<div v-else id="redColor" >Twój adres e-mail jest stanowczo za długi!</div>
<input type="email" v-model="email">

  </div>
</template>

<script>
export default {
data() {
	return {
		email: '',
		password: ''
	}
}
}
</script>

<style>
 #redColor {
	color: red;
 }
</style>
