<template>
  <div id="app">
    <input v-model="name" type="text" placeholder="Escribe tu nombre"> 
    <input v-model="lastName" type="text" placeholder="Escribe tu apellido"> 
    <input v-model="birthDate" type="date">
    <p>Hola {{ fullname }}, tu edad es: {{ age || '#' }} años</p>
    <button @click="format">Formatear</button>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      name: '',
      lastName: '',
      birthDate: '',
    }
  },

  computed: {
    fullname () {
      return `${this.name} ${this.lastName}`
    },
    age () {
      let diff = new Date() - new Date(this.birthDate)
      let age = Math.floor(diff / 1000 / 60 / 60 / 24 / 365)
      return age
    }
  },

  watch: {
    name (val, oldVal) {
      console.log(val, oldVal);
    },

    lastName (val, oldVal) {
      console.log(val, oldVal);
    }
  },
}
</script>

<style lang="scss">

  #app {
    width: 60%;
    background-color: #5D8233;
    color: aliceblue;
    padding: 50px;
    margin: auto;
    text-align: center;
  }

  input {
    margin: 10px;
    padding: 5px;
    outline: none;
  }




/* @import './scss/main.scss'; */

</style>