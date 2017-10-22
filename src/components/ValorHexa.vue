<template>
  <div class="col-12">
    <q-input v-model="converterh" v-on:keyup.enter="verificaHexa" type="text" align="right" inverted color="faded" stack-label="Número Hexadecimal"></q-input>
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
        numhexa: ''
      }
    },
    components: {
      QInput
    },
    computed: {
      converterh () {
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
      }
    }
  }
</script>

<style scoped>

  .q-input{
    margin-top: -7px;
  }

</style>
