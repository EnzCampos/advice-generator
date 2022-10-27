<template class='{{ darkmode ? dark : light}}'>
  <HeaderElem @toggleDarkMode="toggleDarkMode"
    :darkmode= 'this.darkmode'
  />
  <AdviceElem @newAdvice="generateNewAdvice"
    :msg='this.advice'
    :id='this.id'
    :darkmode= 'this.darkmode'
    />
</template>

<script>
import AdviceElem from './components/Advice.vue'
import HeaderElem from './components/Header.vue'

export default {
  name: 'App',
  components: {
    AdviceElem,
    HeaderElem
  },

  data() {
    return {
      advice: '',
      id: '',
      darkmode: true
    }
  },

  async created() {
    const res = await fetch('https://api.adviceslip.com/advice');
    const data = await res.json();
    const { advice,id } = data.slip;
    this.advice = advice
    this.id = id

  },
  methods: {
    toggleDarkMode() {
      this.darkmode = !this.darkmode
    },

    async generateNewAdvice() {
      const res = await fetch('https://api.adviceslip.com/advice');
      const data = await res.json();
      const { advice,id } = data.slip;
      this.advice = advice
      this.id = id
    }
  }
}
</script>

<style>

:root {
  --background-color: hsl(218, 23%, 16%);
  --text-color: white;
  --elements-color: hsl(217, 19%, 24%);
}

:root.light-theme {
  --background-color: white;
  --elements-color: ;
  --text-color: black;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  width: 100vw;
  background-color: var(--background-color)
}
body {
  overflow: hidden;
  margin: 0px;
}

#app + .light {
  --background-color: white;
}

</style>
