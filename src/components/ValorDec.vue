<template>
    <q-input v-model="numDec" disable @click="selecttype" type="number" align="right" inverted color="faded" :class="{ selecionado: classSelect }" stack-label="Número Decimal" ></q-input>
</template>
<script>
  import { QInput } from 'quasar'
  export default {
    name: 'dec',
    props: ['numDec', 'classSelect'],
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
    margin-top: -8px;
  }

</style>
