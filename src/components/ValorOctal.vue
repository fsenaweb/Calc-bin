<template>
  <div class="col-12">
    <q-input v-model="numOctal" disable @click="selecttype" type="number" align="right" inverted color="tertiary" stack-label="Número Octal"></q-input>
  </div>
</template>
<script>
  import { QInput } from 'quasar'
  export default {
    name: 'octal',
    props: ['numOctal'],
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
    margin-top: -7px;
  }

</style>
