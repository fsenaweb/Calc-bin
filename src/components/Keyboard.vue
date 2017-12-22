<template>

  <div style="margin-top: 0.7vh; margin-left: 0.8vmin">
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" :disabled="keyDisabled[0]" @click="press" class=" btn-key-left">D</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" :disabled="keyDisabled[1]" @click="press" class=" btn-key-left">E</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" :disabled="keyDisabled[2]" @click="press" class=" btn-key-left">F</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" :disabled="keyDisabled[3]" @click="press" class=" btn-key-left">A</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" :disabled="keyDisabled[4]" @click="press" class=" btn-key-left">B</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" :disabled="keyDisabled[5]" @click="press" class=" btn-key-left">C</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" :disabled="keyDisabled[6]" @click="press" class=" btn-key-left">7</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" :disabled="keyDisabled[7]" @click="press" class=" btn-key-left">8</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" :disabled="keyDisabled[8]" @click="press" class=" btn-key-left">9</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" :disabled="keyDisabled[9]" @click="press" class=" btn-key-left">4</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" :disabled="keyDisabled[10]" @click="press" class=" btn-key-left">5</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" :disabled="keyDisabled[11]" @click="press" class=" btn-key-left">6</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" :disabled="keyDisabled[12]" @click="press" class=" btn-key-left">1</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" :disabled="keyDisabled[13]" @click="press" class=" btn-key-left">2</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" :disabled="keyDisabled[14]" @click="press" class=" btn-key-left">3</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" :disabled="keyDisabled[15]" @click="press" class=" btn-key-left">0</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" style="background-color: green; color: white" @click="press" class=" btn-key-left">OK</q-btn>
    <q-btn flat :style="{ height: tamanhobtn + 'em' }" style="color: #FFF" @click="press" class=" btn-key-left">limpar</q-btn>
  </div>

</template>

<script>
  import {QBtn} from 'quasar'
  export default {
    name: 'keyboard',
    props: ['keyDisabled'],
    data () {
      return {
        tamanhobtn: 3
      }
    },
    components: {
      QBtn
    },
    methods: {
      press (event) {
        let key = event.target.innerText
        this.$emit('tecla', key)
      }
    },
    mounted () {
      if (screen.height <= 600) {
        this.tamanhobtn = '2.95'
      }
      else if ((screen.height > 600) && (screen.height <= 640)) {
        this.tamanhobtn = '2.75'
      }
      else if ((screen.height > 640) && (screen.height <= 670)) {
        this.tamanhobtn = '3.1'
      }
      else if (screen.height === 732) {
        this.tamanhobtn = '3.4'
      }
      else if (screen.height === 667) {
        this.tamanhobtn = '3.1'
      }
      else if ((screen.height > 670) && (screen.height <= 740)) {
        this.tamanhobtn = '4.2'
      }
      else if ((screen.height > 740) && (screen.height <= 960)) {
        this.tamanhobtn = '4'
      }
      else if (screen.height > 960) {
        this.tamanhobtn = '5.7'
      }
      console.log(screen.height)
    }
  }
</script>

<style scoped>

  .btn-key-left{
    width: 31vw;
    margin: 0.5vmin;
    background: #5F5F5F;
    text-align: center;
    padding: 1%;
    color: #FFF;
    border-radius: 7px;
  }

  .activeClass{
    background-color: orange;
  }

</style>
