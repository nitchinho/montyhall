<template>
  <div id="app">
    <h1>Problema de Monty Hall</h1>
    <DoorComponent number="1" :hasGift="false"></DoorComponent>    
  </div>

</template>

<script>
import DoorComponent from './components/DoorComponent.vue';

export default {
  name: 'App',
  components: {
    DoorComponent
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
  background: linear-gradient(to right, #f1f2b5, #135058); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
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

</style>
