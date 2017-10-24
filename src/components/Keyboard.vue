<template>

  <div class="row" style="margin-bottom: 2%">
    <q-btn flat style="color: #FFF" class="col-4 btn-key-left">D</q-btn>
    <q-btn flat style="color: #FFF" class="col-4 btn-key-left">E</q-btn>
    <q-btn flat style="color: #FFF" class="col-4 btn-key-left">F</q-btn>
    <q-btn flat style="color: #FFF" class="col-4 btn-key-left">A</q-btn>
    <q-btn flat style="color: #FFF" class="col-4 btn-key-left">B</q-btn>
    <q-btn flat style="color: #FFF" class="col-4 btn-key-left">C</q-btn>
    <q-btn flat style="color: #FFF" class="col-4 btn-key-left">7</q-btn>
    <q-btn flat style="color: #FFF" class="col-4 btn-key-left">8</q-btn>
    <q-btn flat style="color: #FFF" class="col-4 btn-key-left">9</q-btn>
    <q-btn flat style="color: #FFF" class="col-4 btn-key-left">4</q-btn>
    <q-btn flat style="color: #FFF" class="col-4 btn-key-left">5</q-btn>
    <q-btn flat style="color: #FFF" class="col-4 btn-key-left">6</q-btn>
    <q-btn flat style="color: #FFF" class="col-4 btn-key-left">1</q-btn>
    <q-btn flat style="color: #FFF" class="col-4 btn-key-left">2</q-btn>
    <q-btn flat style="color: #FFF" class="col-4 btn-key-left">3</q-btn>
    <q-btn flat style="color: #FFF" class="col-4 btn-key-left">0</q-btn>
    <q-btn flat style="color: #FFF" class="col-8 btn-key-left">limpar</q-btn>
  </div>

</template>

<script>
  import {QBtn} from 'quasar'
  export default {
    name: 'keyboard',
    data () {
      return {
        activeClass: false
      }
    },
    components: {
      QBtn
    },
    methods: {
      clicando () {
        this.activeClass = true
      }
    }
  }
</script>

<style scoped>

  .btn-key-left{
    background: #4A4A4A;
    height: 35px;
    border-left: 1px solid #6A6A6A;
    border-top: 1px solid #6A6A6A;
    text-align: center;
    padding: 2.5%;
    color: #FFF;
  }

  .btn-key-right{
    background: #4A4A4A;
    height: 35px;
    border-left: 1px solid #6A6A6A;
    border-top: 1px solid #6A6A6A;
    border-right: 1px solid #6A6A6A;
    text-align: center;
    padding: 2.5%;
    color: #FFF;
  }

  .btn-key-clear{
    background: #1F1F21;
    height: 35px;
    border-left: 1px solid #6A6A6A;
    border-top: 1px solid #6A6A6A;
    border-right: 1px solid #6A6A6A;
    text-align: center;
    padding: 2.5%;
    color: #FFF;
  }

  .activeClass{
    background-color: orange;
  }

</style>
