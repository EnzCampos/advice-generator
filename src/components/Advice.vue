<template>
  <div class="advice-div">
    <p>Advice #{{id}}</p>
    <h2>{{ msg }}</h2>
    <img src="../assets/pattern-divider-desktop.svg" alt="Divider Img" class='img-divider'/>
    <div class="dice-div" @click="$emit('newAdvice')">
      <img src="../assets/icon-dice.svg" alt="Dice Img" class='dice'/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AdviceElem',
  props: ['msg','id']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.advice-div {
  background-color: hsl(217, 19%, 24%);
  width: 20%;
  padding: 30px;
  border-radius: 15px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
h2 {
  color: var(--text-color)
}
p {
  color: hsl(150, 100%, 66%)
}
.img-divider {
  margin-top: 15px;
  width: 95%;
}
.dice-img {
  width: 20px;
}
.dice-div {
  margin-top: -30px;
  position: relative;
  top: 55px;
  width: 20px;
  height: 20px;
  border: 15px solid hsl(150, 100%, 66%);
  border-radius: 50%;
}
.dice {
  width: 20px;
  background-color: hsl(150, 100%, 66%);
}
.dice-div:hover {
  box-shadow: 0px 0px 15px 5px hsl(150, 100%, 66%);
}
</style>
