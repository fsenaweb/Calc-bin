<template>

  <div class="row">
    <q-btn flat :style="{color: '#FFF', height: tamanhobtn + 'em' }" :disabled="keyDisabled[0]" @click="press" class="col-4 btn-key-left">D</q-btn>
    <q-btn flat :style="{color: '#FFF', height: tamanhobtn + 'em' }" :disabled="keyDisabled[1]" @click="press" class="col-4 btn-key-left">E</q-btn>
    <q-btn flat :style="{color: '#FFF', height: tamanhobtn + 'em' }" :disabled="keyDisabled[2]" @click="press" class="col-4 btn-key-left">F</q-btn>
    <q-btn flat :style="{color: '#FFF', height: tamanhobtn + 'em' }" :disabled="keyDisabled[3]" @click="press" class="col-4 btn-key-left">A</q-btn>
    <q-btn flat :style="{color: '#FFF', height: tamanhobtn + 'em' }" :disabled="keyDisabled[4]" @click="press" class="col-4 btn-key-left">B</q-btn>
    <q-btn flat :style="{color: '#FFF', height: tamanhobtn + 'em' }" :disabled="keyDisabled[5]" @click="press" class="col-4 btn-key-left">C</q-btn>
    <q-btn flat :style="{color: '#FFF', height: tamanhobtn + 'em' }" :disabled="keyDisabled[6]" @click="press" class="col-4 btn-key-left">7</q-btn>
    <q-btn flat :style="{color: '#FFF', height: tamanhobtn + 'em' }" :disabled="keyDisabled[7]" @click="press" class="col-4 btn-key-left">8</q-btn>
    <q-btn flat :style="{color: '#FFF', height: tamanhobtn + 'em' }" :disabled="keyDisabled[8]" @click="press" class="col-4 btn-key-left">9</q-btn>
    <q-btn flat :style="{color: '#FFF', height: tamanhobtn + 'em' }" :disabled="keyDisabled[9]" @click="press" class="col-4 btn-key-left">4</q-btn>
    <q-btn flat :style="{color: '#FFF', height: tamanhobtn + 'em' }" :disabled="keyDisabled[10]" @click="press" class="col-4 btn-key-left">5</q-btn>
    <q-btn flat :style="{color: '#FFF', height: tamanhobtn + 'em' }" :disabled="keyDisabled[11]" @click="press" class="col-4 btn-key-left">6</q-btn>
    <q-btn flat :style="{color: '#FFF', height: tamanhobtn + 'em' }" :disabled="keyDisabled[12]" @click="press" class="col-4 btn-key-left">1</q-btn>
    <q-btn flat :style="{color: '#FFF', height: tamanhobtn + 'em' }" :disabled="keyDisabled[13]" @click="press" class="col-4 btn-key-left">2</q-btn>
    <q-btn flat :style="{color: '#FFF', height: tamanhobtn + 'em' }" :disabled="keyDisabled[14]" @click="press" class="col-4 btn-key-left">3</q-btn>
    <q-btn flat :style="{color: '#FFF', height: tamanhobtn + 'em' }" :disabled="keyDisabled[15]" @click="press" class="col-4 btn-key-left">0</q-btn>
    <q-btn flat style="background-color: green; color: white" @click="press" class="col-4 btn-key-left">OK</q-btn>
    <q-btn flat style="color: #FFF" @click="press" class="col-4 btn-key-left">limpar</q-btn>
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
        this.tamanhobtn = '3.7'
      }
      else if ((screen.height > 640) && (screen.height <= 670)) {
        this.tamanhobtn = '4'
      }
      else if ((screen.height > 670) && (screen.height <= 740)) {
        this.tamanhobtn = '4.75'
      }
      else if (screen.height === 732) {
        this.tamanhobtn = '3.8'
      }
      else if ((screen.height > 740) && (screen.height <= 960)) {
        this.tamanhobtn = '7.15'
      }
      else if (screen.height > 960) {
        this.tamanhobtn = '10'
      }
      console.log(screen.height)
    }
  }
</script>

<style scoped>

  .btn-key-left{
    background: #5F5F5F;
    border-left: 1px solid #6A6A6A;
    border-top: 1px solid #6A6A6A;
    text-align: center;
    padding: 2.5%;
    color: #FFF;
  }

  .btn-key-right{
    background: #5F5F5F;
    height: 35px;
    border-left: 1px solid #6A6A6A;
    border-top: 1px solid #6A6A6A;
    border-right: 1px solid #6A6A6A;
    text-align: center;
    padding: 2.5%;
    color: #FFF;
  }

  .btn-key-clear{
    background: #1F1F21;
    height: 35px;
    border-left: 1px solid #6A6A6A;
    border-top: 1px solid #6A6A6A;
    border-right: 1px solid #6A6A6A;
    text-align: center;
    padding: 2.5%;
    color: #FFF;
  }

  .activeClass{
    background-color: orange;
  }

</style>
