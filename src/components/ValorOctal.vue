<template>
  <div class="col-12">
    <q-input v-model="converter" v-on:keyup="verificaOctal" type="number" align="right" inverted color="primary" stack-label="Número Octal"></q-input>
  </div>
</template>
<script>
  import { QInput } from 'quasar'
  export default {
    name: 'octal',
    props: ['numPrincipal'],
    data () {
      return {
        octal: ''
      }
    },
    components: {
      QInput
    },
    computed: {
      converter () {
        let decimal = this.numPrincipal
        let octal = decimal.toString(8)
        return octal
      }
    },
    methods: {
      verificaOctal: function ($event) {
        if (($event.keyCode >= 48 && $event.keyCode <= 55)) {
          this.numOctal = $event.target.value
          this.numBack = this.numOctal
        }
        else {
          if (this.numBack === undefined) {
            this.numOctal = this.numBack
          }
          this.numOctal = this.numBack
        }
        let tasko = this.numOctal
        this.$emit('valueoctal', tasko)
      }
    }
  }
</script>

<style scoped>

  .q-input{
    margin-top: -7px;
  }

</style>
