<template>

  <div class="row" style="margin-bottom: 2%">
    <div class="col-4 btn-key-left">D</div>
    <div class="col-4 btn-key-left">E</div>
    <div class="col-4 btn-key-right">F</div>
    <div class="col-4 btn-key-left">A</div>
    <div class="col-4 btn-key-left">B</div>
    <div class="col-4 btn-key-right">C</div>
    <div class="col-4 btn-key-left">7</div>
    <div class="col-4 btn-key-left">8</div>
    <div class="col-4 btn-key-right">9</div>
    <div class="col-4 btn-key-left">4</div>
    <div class="col-4 btn-key-left">5</div>
    <div class="col-4 btn-key-right">6</div>
    <div class="col-4 btn-key-left">1</div>
    <div class="col-4 btn-key-left">2</div>
    <div class="col-4 btn-key-right">3</div>
    <div class="col-4 btn-key-left">0</div>
    <div class="col-8 btn-key-clear">limpar</div>
  </div>

</template>

<script>
	export default {
	  name: 'keyboard'
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

</style>
