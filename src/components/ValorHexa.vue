<template>
  <div class="col-12">
    <q-input v-model="converter" disable @click="selecttype" @keyup.enter="verificaHexa" type="text" align="right" inverted color="faded" stack-label="Número Hexadecimal"></q-input>
  </div>
</template>
<script>
  import { QInput } from 'quasar'
  export default {
    name: 'hexa',
    props: ['numPrincipal'],
    data () {
      return {
        hexadecimal: '',
        numhexa: false
      }
    },
    components: {
      QInput
    },
    computed: {
      converter () {
        let decimal = this.numPrincipal
        let numhexa = decimal.toString(16)
        return numhexa
      }
    },
    methods: {
      verificaHexa: function ($event) {
        this.hexadecimal = $event.target.value
        let taskh = this.hexadecimal
        this.$emit('valuehexa', taskh)
      },
      selecttype () {
        let selectInput = 'inputHexa'
        this.$emit('selectInput', selectInput)
      }
    }
  }
</script>

<style scoped>

  .q-input{
    margin-top: -7px;
  }

</style>
