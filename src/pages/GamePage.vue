<template>
  <q-page style="background: #4DC5B0">
    <div class = "title">
      <p class = "text"> Викторина </p>
    </div>
    <div>
      <q-chip class = "block">
        <q-avatar>
          <img style = "position: absolute; scale: 4; top: -60px; left: -5px;" src="~assets/icon.svg">
        </q-avatar>
        <p class = "textGame"> Какой из этих методов лучше всего помогает защитить аккаунты от несанкционированного доступа?</p>
      </q-chip>
    </div>
  </q-page>
</template>

<script>

</script>

<style lang="scss" scoped>
  .title {
    background-color: #FAAA2E;
    border-radius: 0 0 30px 30px;
    height: 60px;
  }
  .text {
    font-family: Roboto;
    color: #3A316A;
    font-size: 45px;
    left: 50%;
    transform: translate(-50%, 0);
    position: absolute;
    top: -8px;
  }
  .block {
    // max-width: 550px;
    // width: 85%;
    // height: 120px;
    // background: #FAAA2E;
    // margin-top: 85px;
    // border-radius: 30px;
    // left: 50%;
    // position: absolute;
    // transform: translate(-50%, 0);
    // align-content: center;
    background-color: #FAAA2E;
    max-width: 550px;
    width: 85%;
    height: 120px;
    border-radius: 30px;
    left: 50%;
    transform: translate(-50%, 0);
    align-content: center;
    margin-top: 50px;
  }
  .textGame {
    text-align: center;
    width: 100%;
    font-size: 20px;
    font-family: Roboto;
    line-height: 25px;
    max-width: 550px;
    white-space: break-spaces;
    left: 0;
    position: absolute;
  }
</style>