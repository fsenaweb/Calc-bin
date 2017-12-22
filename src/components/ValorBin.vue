<template>
  <q-input v-model="numBinario" disable @click="selecttype" type="text" align="right" inverted color="tertiary" :class="{ selecionado: classSelect }" stack-label="Número Binário" ></q-input>
</template>

<script>
  import { QInput } from 'quasar'

  export default {
    name: 'bin',
    props: ['numBinario', 'classSelect'],
    data () {
      return {
      }
    },
    components: {
      QInput
    },
    computed: {
      converter () {
        // let decimal = this.numPrincipal
        // this.binario = decimal.toString(2)
        return this.binario
      }
    },
    methods: {
      selecttype () {
        let selectInput = 'inputBin'
        this.$emit('selectInput', selectInput)
      }
    }
  }
</script>

<style scoped>

  .q-input{
    margin-top: 0;
  }

</style>
