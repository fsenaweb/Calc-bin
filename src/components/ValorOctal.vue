<template>
    <q-input v-model="numOctal" disable @click="selecttype" type="number" align="right" inverted color="tertiary" :class="{ selecionado: classSelect }" stack-label="Número Octal"></q-input>
</template>
<script>
  import { QInput } from 'quasar'
  export default {
    name: 'octal',
    props: ['numOctal', 'classSelect'],
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
        // let octal = decimal.toString(8)
        // return octal
      }
    },
    methods: {
      selecttype () {
        let selectInput = 'inputOct'
        this.$emit('selectInput', selectInput)
      }
    }
  }
</script>

<style scoped>

  .q-input{
    margin-top: -8px;
  }

</style>
