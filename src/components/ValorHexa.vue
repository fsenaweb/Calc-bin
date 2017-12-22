<template>
    <q-input v-model="numHexa" disable @click="selecttype" @keyup.enter="verificaHexa" type="text" align="right" :class="{ selecionado: classSelect }" inverted color="faded" stack-label="Número Hexadecimal"></q-input>
</template>
<script>
  import { QInput } from 'quasar'
  export default {
    name: 'hexa',
    props: ['numHexa', 'classSelect'],
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
    margin-top: -8px;
  }
</style>
