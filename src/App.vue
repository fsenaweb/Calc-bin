<template>
  <!-- Don't drop "q-app" class -->
  <div id="q-app">
    <div class="row">
      <div class="col-1"></div>
      <div class="col-10">
      <div>
        <img src="~assets/logo.png" class="responsive">
      </div>
    <br>
      <div class="row">
        <valor-bin @valuebin="addBinary" :num-principal="numPrincipal"></valor-bin>
        <valor-hexa @valuehexa="addHexa" :num-principal="numPrincipal"></valor-hexa>
        <valor-octal @valueoctal="addOctal" :num-principal="numPrincipal"></valor-octal>
      </div>
    <q-input v-model="numGeral" type="text" @keyup.enter="sendNumber" align="right" inverted color="dark" stack-label="Digite um número decimal" ></q-input>
      </div>
      <div class="col-1"></div>
    </div>
  </div>
</template>

<script>
import { QLayout, QToolbar, QToolbarTitle, QInput } from 'quasar'
import ValorOctal from './components/ValorOctal'
import ValorHexa from './components/ValorHexa'
import ValorBin from './components/ValorBin'
import ValorDec from './components/ValorDec'

export default {
  data () {
    return {
      numBin: '',
      numHexa: '',
      numOctal: '',
      numDec: '',
      numGeral: '',
      numPrincipal: ''
    }
  },
  components: {
    ValorOctal,
    ValorHexa,
    ValorBin,
    ValorDec,
    QLayout,
    QToolbar,
    QToolbarTitle,
    QInput
  },
  methods: {
    addBinary (taskb) {
      let binario = taskb
      let decimal = parseInt(binario, 2)
      this.numGeral = decimal
      console.log(taskb)
    },
    addHexa (taskh) {
      this.numHexa = taskh
      console.log(this.numHexa)
    },
    addOctal (tasko) {
      this.numOctal = tasko
      console.log(this.numOctal)
    },
    addDec (taskd) {
      this.numDec = taskd
      console.log(this.numDec)
    },
    sendNumber () {
      let decimal = parseInt(this.numGeral)
      this.numPrincipal = decimal
    }
  }
}
</script>

<style>

  .q-input{
    height: 70px;
  }

</style>
