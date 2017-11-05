<template>
  <div class="col-12">
    <q-input v-model="numDec" disable @click="selecttype" type="number" align="right" inverted color="faded" stack-label="Número Decimal" ></q-input>
  </div>
</template>
<script>
  import { QInput } from 'quasar'
  export default {
    name: 'dec',
    props: ['numDec'],
    data () {
      return {
      }
    },
    components: {
      QInput
    },
    methods: {
      selecttype () {
        let selectInput = 'inputDec'
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
