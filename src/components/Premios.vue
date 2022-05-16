<template>
  <div class="premio">
      <div class="laco-premio-1"></div>
      <div class="laco-premio-2"></div>
      <div class="tampa-do-premio"></div>
      <div class="corpo-do-presente"></div>
  </div>
</template>

<script>
export default {
name: 'premios-',
}
</script>

<style>
  .premio{
    display: flex;
    flex-direction: column;
    align-items: center;
    z-index: 10;
    position: relative;
  }

  .premio .tampa-do-premio{
    width: 100px;
    height: 25px;
    background-color: #ffea02;
  }

  .premio .corpo-do-presente{
    width: 90px;
    height: 60px;
    background-color: #ab9d03;
  }

  .premio .laco-premio-1{
    position: absolute;
    width: 15px;
    height: 85px;
    background-color: #ff0000;
  }

  .premio .laco-premio-2{
    position: absolute;
    top: 40px;
    width: 90px;
    height: 15px;
    background-color: #ff0000;
  }
</style>