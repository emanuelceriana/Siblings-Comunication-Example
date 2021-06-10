<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" height="50">
    <h2>Siblings communication</h2>
    <component-1 :component2Text="text2" @updateText="(text) => {updateText(text,1)}" />
    <component-2 :component1Text="text1" @updateText="(text) => {updateText(text,2)}" />
  </div>
</template>

<script>
import Component1 from './components/Component1.vue'
import Component2 from './components/Component2.vue'

export default {
  name: 'App',
  components: {
    Component1,
    Component2
  },
  data() {
    return {
      text1: '',
      text2: '',
    }
  },
  methods: {
    updateText(text,number){
      switch(number) {
        case 1:
          this.text1 = text;
          break;
        case 2:
          this.text2 = text
          break;
      }
    }
  }
}
</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body{
  background: black;
}
h1,h2,h3,h4,h5,h6 {
  color: white;
}
.row {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
}
.col {
    padding: 10px;
}
</style>
