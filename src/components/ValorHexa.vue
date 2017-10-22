<template>
  <div class="col-12">
    <q-input v-model="converter" v-on:keyup="verificaHexa" type="text" align="right" inverted color="faded" stack-label="Número Hexadecimal"></q-input>
  </div>
</template>
<script>
  import { QInput } from 'quasar'
  export default {
    name: 'hexa',
    props: ['numPrincipal'],
    data () {
      return {
        numhexa: ''
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
        if (($event.keyCode >= 48 && $event.keyCode <= 70)) {
          this.numHexa = $event.target.value
          this.numBack = this.numHexa
        }
        else {
          if (this.numBack === undefined) {
            this.numHexa = this.numBack
          }
          this.numHexa = this.numBack
        }
        let taskh = this.numHexa
        this.$emit('valuehexa', taskh)
      }
    },
    filters: {
      capitalize: function (numhexa) {
        if (!numhexa) return ''
        numhexa = numhexa.toString()
        return numhexa.toUpperCase()
      }
    }
  }
</script>

<style scoped>

  .q-input{
    margin-top: -7px;
  }

</style>
