<template>
  <div class="col-12">
    <q-input v-model="numDec" v-on:keyup="verificaDec" type="number" align="right" inverted color="positive" stack-label="Número Decimal" ></q-input>
  </div>
</template>
<script>
  import { QInput } from 'quasar'
  export default {
    name: 'dec',
    data () {
      return {
        numDec: ''
      }
    },
    components: {
      QInput
    },
    methods: {
      verificaDec: function () {
        let taskd = this.numDec
        this.$emit('valuedec', taskd)
      }
    }
  }
</script>

<style scoped>

  .q-input{
    margin-top: -7px;
  }

</style>
