<template>
  <div>
 
<!-- 
<h1>Twój e-mail to: {{ email }}</h1>
<div v-if="email.length == 0">podaj swoj e-mail</div>
<div v-else-if="email.length < 10 & email.length > 0">Ale masz krótki adres!</div>
<div v-else-if="email.length < 25">Twój adres e-mail jest w sam raz.</div>
<div v-else id="redColor" >Twój adres e-mail jest stanowczo za długi!</div>
<input type="email" v-model="email" @keyup.enter="alertMyEmail()">
<button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button>
-->

<h1>Witaj w systemie do zapisów na zajęcia</h1>
<div v-if="!email">
<login-form @login="logMeIn($event)" button-label="wejdź"></login-form>
<login-form @login="logMeIn($event)" button-label="wleć"></login-form>
<login-form @login="logMeIn($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>
</div>

<!--
<div v-if="!loggedIn">Zaloguj się e-mailem 
<input type="email" v-model="email" @keyup.enter="enterMyEmail()">
<button @click="enterMyEmail()">Wchodzę</button>
</div>
-->

<div v-else>
	<h3>Witaj {{ email }}</h3>
	<button @click="logout()">Wyloguj</button>
</div>

  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
components: {LoginForm},
data() {
	return {
		email: '',
		loggedIn: false,
	}
}

,methods: {
  alertMyEmail() {
    alert(this.email);
  },
  
  enterMyEmail() {
    this.loggedIn = true;
  },
  
    logMeIn(username) {
	this.email = username;
  },
  
  logout() {
	this.email = '',
    this.loggedIn = false;
  }
  
  
}



}
</script>

<style>
 #redColor {
	color: red;
 }
</style>
