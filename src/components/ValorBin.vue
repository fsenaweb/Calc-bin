<template>
  <div class="col-12">
    <q-input v-model="converter" disable @click="selecttype" @keyup.enter="verificabin" type="text" align="right" inverted color="tertiary" stack-label="Número Binário" ></q-input>
  </div>
</template>

<script>
  import { QInput } from 'quasar'

  export default {
    name: 'bin',
    props: ['numPrincipal'],
    data () {
      return {
        binario: '',
        numBack: ''
      }
    },
    components: {
      QInput
    },
    computed: {
      converter () {
        let decimal = this.numPrincipal
        this.binario = decimal.toString(2)
        return this.binario
      }
    },
    methods: {
      verificabin: function ($event) {
        this.binario = $event.target.value
        let taskb = this.binario
        this.$emit('valuebin', taskb)
      },
      selecttype () {
        let selectInput = 'inputBin'
        this.$emit('selectInput', selectInput)
      }
    }
  }
</script>

<style scoped>

  .q-input{
    margin-top: 5px;
  }

</style>
