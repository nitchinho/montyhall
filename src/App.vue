<template>
  <div id="app">
    <h1>Problema de Monty Hall</h1>
    <div class="form">
      <div v-if="!started">
        <label for="portsAmount"> Quantas Portas? </label>
        <input type="text" id="portsAmount" size="3" v-model.number="portsAmount">
      </div>
      <div v-if="!started">
        <label for="selectedPort"> Qual porta será a premiada? </label>
        <input type="text" id="selectedPort" size="3" v-model.number="selectedPort">
      </div>
      <button v-if="!started" @click="started = true">Iniciar</button>
      <button v-if="started" @click="started = false, geraPorta(portsAmount, selectedPort)">Reiniciar</button>
    </div>
    <div class="doors" v-if="started">
      <div v-for="i in portsAmount" :key="i">
        <DoorComponent :hasGift="i === selectedPort" :number="i" />
      </div>
    </div>
  </div>

</template>

<script>
import DoorComponent from './components/DoorComponent.vue';

export default {
  name: 'App',
  components: {
    DoorComponent
  },
  data: function () {
    return {
      started: false,
      portsAmount: 3,
      selectedPort: null
    }
  },
  methods: {
    geraPorta(porta, selectedPort) {
      this.portaPremiada = Math.floor(Math.random() * porta) + 1; // Gera um número aleatório entre 1 e numPortas
      this.portaPremiada = selectedPort
    }
  }

}
</script>

<style>
* {
  box-sizing: border-box;
  font-family: 'Montserrat', sans-serif;
}

body {
  color: #fff;
  background: linear-gradient(to right, #f1f2b5, #135058);
  /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
}

#app h1 {
  border: 1px solid #000;
  background-color: #0004;
  padding: 20px;
  margin-bottom: 60px;
}

.form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: self-start;
  margin-bottom: 40px;
}

.form, .form input, .form button {
  margin-bottom: 10px;
  font-size: 1.6rem;
}

.doors {
  align-self: stretch;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;


}
</style>
