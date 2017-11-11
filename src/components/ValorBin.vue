<template>
  <div class="col-12">
    <q-input v-model="numBinario" disable @click="selecttype" type="text" align="right" inverted color="tertiary" stack-label="Número Binário" >

    </q-input>
  </div>
</template>

<script>
  import { QInput } from 'quasar'

  export default {
    name: 'bin',
    props: ['numBinario'],
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
    margin-top: 5px;
  }

</style>
