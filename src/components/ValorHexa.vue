<template>
  <div class="col-12">
    <q-input v-model="numHexa" disable @click="selecttype" @keyup.enter="verificaHexa" type="text" align="right" inverted color="faded" stack-label="Número Hexadecimal"></q-input>
  </div>
</template>
<script>
  import { QInput } from 'quasar'
  export default {
    name: 'hexa',
    props: ['numHexa'],
    data () {
      return {
      }
    },
    components: {
      QInput
    },
    methods: {
      selecttype () {
        let selectInput = 'inputHexa'
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
