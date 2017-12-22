<template>
  <!-- Don't drop "q-app" class -->
  <div>
      <img src="~assets/logo.png" class="responsive">
      <div class="tela-numeros">
        <valor-bin @selectInput="seleciona" :class-select="classBin" :num-binario="numBin"></valor-bin>
        <valor-hexa @selectInput="seleciona" :class-select="classHex" :num-hexa="numHexa"></valor-hexa>
        <valor-octal @selectInput="seleciona" :class-select="classOct" :num-octal="numOctal"></valor-octal>
        <valor-dec @selectInput="seleciona" :class-select="classDec" :num-dec="numDec"></valor-dec>
      </div>
      <keyboard :key-disabled="keyDisabled" @tecla="digitado"></keyboard>
  </div>
</template>

<script>
import { QLayout, QToolbar, QToolbarTitle, QInput, Dialog } from 'quasar'
import ValorOctal from './components/ValorOctal'
import ValorHexa from './components/ValorHexa'
import ValorBin from './components/ValorBin'
import ValorDec from './components/ValorDec'
import Keyboard from './components/Keyboard'

export default {
  data () {
    return {
      numBin: '',
      numHexa: '',
      numOctal: '',
      numDec: '',
      numGeral: '',
      numPrincipal: '',
      keyDisabled: [],
      selectInput: '',
      classBin: false,
      classHex: false,
      classOct: false,
      classDec: false
    }
  },
  components: {
    ValorOctal,
    ValorHexa,
    ValorBin,
    ValorDec,
    Keyboard,
    QLayout,
    QToolbar,
    QToolbarTitle,
    QInput,
    Dialog
  },
  methods: {
    seleciona (selectInput) {
      if (selectInput === 'inputBin') {
        this.numHexa = ''
        this.numOctal = ''
        this.numDec = ''
        this.selectInput = 'inputBin'
        this.classBin = true
        this.classHex = false
        this.classOct = false
        this.classDec = false
        this.keyDisabled = [
          true, // D
          true, // E
          true, // F
          true, // A
          true, // B
          true, // C
          true, // 7
          true, // 8
          true, // 9
          true, // 4
          true, // 5
          true, // 6
          false, // 1
          true, // 2
          true, // 3
          false // 0
        ]
      }
      else if (selectInput === 'inputHexa') {
        this.numBin = ''
        this.numOctal = ''
        this.numDec = ''
        this.selectInput = 'inputHexa'
        this.classBin = false
        this.classHex = true
        this.classOct = false
        this.classDec = false
        this.keyDisabled = [
          false, // D
          false, // E
          false, // F
          false, // A
          false, // B
          false, // C
          false, // 7
          false, // 8
          false, // 9
          false, // 4
          false, // 5
          false, // 6
          false, // 1
          false, // 2
          false, // 3
          false // 0
        ]
      }
      else if (selectInput === 'inputOct') {
        this.numHexa = ''
        this.numBin = ''
        this.numDec = ''
        this.selectInput = 'inputOct'
        this.classBin = false
        this.classHex = false
        this.classOct = true
        this.classDec = false
        this.keyDisabled = [
          true, // D
          true, // E
          true, // F
          true, // A
          true, // B
          true, // C
          false, // 7
          true, // 8
          true, // 9
          false, // 4
          false, // 5
          false, // 6
          false, // 1
          false, // 2
          false, // 3
          false // 0
        ]
      }
      else if (selectInput === 'inputDec') {
        this.numHexa = ''
        this.numOctal = ''
        this.numBin = ''
        this.selectInput = 'inputDec'
        this.classBin = false
        this.classHex = false
        this.classOct = false
        this.classDec = true
        this.keyDisabled = [
          true, // D
          true, // E
          true, // F
          true, // A
          true, // B
          true, // C
          false, // 7
          false, // 8
          false, // 9
          false, // 4
          false, // 5
          false, // 6
          false, // 1
          false, // 2
          false, // 3
          false // 0
        ]
      }
    },
    digitado (key) {
      if (this.selectInput === 'inputBin') {
        if (key === 'OK') {
          let convertNum = this.addBinary(this.numBin)
          this.numHexa = this.addHexa(convertNum).toUpperCase()
          this.numOctal = this.addOctal(convertNum)
          this.numDec = convertNum
        }
        else if (key === 'LIMPAR') {
          this.numBin = ''
          this.numHexa = ''
          this.numOctal = ''
          this.numDec = ''
        }
        else {
          this.numBin += key
        }
      }
      else if (this.selectInput === 'inputHexa') {
        if (key === 'OK') {
          let convertNum = this.hexa2Dec(this.numHexa)
          this.numBin = this.dec2Bin(convertNum)
          this.numOctal = this.addOctal(convertNum)
          this.numDec = convertNum
        }
        else if (key === 'LIMPAR') {
          this.numBin = ''
          this.numHexa = ''
          this.numOctal = ''
          this.numDec = ''
        }
        else {
          this.numHexa += key
        }
      }
      else if (this.selectInput === 'inputOct') {
        if (key === 'OK') {
          let convertNum = this.oct2dec(this.numOctal)
          this.numBin = this.dec2Bin(convertNum)
          this.numHexa = this.addHexa(convertNum).toUpperCase()
          this.numDec = convertNum
        }
        else if (key === 'LIMPAR') {
          this.numBin = ''
          this.numHexa = ''
          this.numOctal = ''
          this.numDec = ''
        }
        else {
          this.numOctal += key
        }
      }
      else if (this.selectInput === 'inputDec') {
        if (key === 'OK') {
          let convertNum = this.dec2Bin(this.numDec)
          this.numBin = convertNum
          convertNum = this.addBinary(convertNum)
          this.numHexa = this.addHexa(convertNum).toUpperCase()
          this.numOctal = this.addOctal(convertNum)
        }
        else if (key === 'LIMPAR') {
          this.numBin = ''
          this.numHexa = ''
          this.numOctal = ''
          this.numDec = ''
        }
        else {
          this.numDec += key
        }
      }
      else {
        Dialog.create({
          title: 'Atenção',
          message: 'Selecione um tipo de numeração!'
        })
      }
    },
    addBinary (taskb) { // convert binario para decimal
      let binario = taskb
      let decimal = parseInt(binario, 2)
      return decimal
    },
    addHexa (taskh) { // convert binario para hexadecimal
      let decimal = taskh
      let hexadecimal = decimal.toString(16)
      return hexadecimal
    },
    addOctal (tasko) { // convert binario para octal
      let decimal = tasko
      let octal = decimal.toString(8)
      return octal
    },
    dec2Bin (taks) { // convert decimal para binario
      let decimal = parseInt(taks, 10)
      let binario = decimal.toString(2)
      return binario
    },
    hexa2Dec (task) { // convert hexadecimal para decimal
      let valor = task
      let decimal = parseInt(valor, 16)
      return decimal
    },
    oct2dec (task) {
      let octal = task
      let decimal = parseInt(octal, 8)
      return decimal
    }
  }
}
</script>

<style>

  body{
    background-color: #000;
  }

  img{
    margin: 0;
    padding: 0;
  }

  .tela-numeros {
    height: 83vmin;
    margin: 0;
    padding: 0;
    margin-top: -1vh;
    border: 6px solid #CCC;
    border-top: 12px solid #CCC;
    border-bottom: 8px solid #CCC;
  }

  .q-input{
    height: 19.5vmin;
    border-radius: 0;
  }

  .active {
    border-left: 5px solid #ABEAFE;
  }

  .selecionado{
    border-left: 9px solid #FFF;
  }


</style>
