<template>
  <q-page style="background: #4DC5B0; overflow: hidden;">
    <div class = "title">
      <p class = "text"> Викторина </p>
    </div>
    <div>
      <q-chip class = "block" :ripple="false">
        <q-avatar>
          <img class = "img" src="~assets/icon.svg">
        </q-avatar>
        <p class = "textGame"> Какой из этих методов лучше всего помогает защитить аккаунты от несанкционированного доступа?</p>
      </q-chip>
    </div>
    <div style = "display: grid;">
      <q-btn push class="button" :ripple="false" @click="selectOption('option1')">
        <div class="row items-center no-wrap" style="width: 100%;">
          <q-avatar size="42px" style="margin: 2px;">
            <img :src="selected === 'option1' ? option1Img : defaultImg" />
          </q-avatar>
          <div class="text-center">
            <span class = "textAnswer"> Использование одного пароля для всех аккаунтов </span>
          </div>
        </div>
      </q-btn>
      <q-btn push class="button" :ripple="false" @click="methodAll('option1')">
        <div class="row items-center no-wrap" style="width: 100%;">
          <q-avatar size="42px" style="margin: 2px;">
            <img :src="selected === 'option1' ? option2Img : defaultImg">
          </q-avatar>
          <div class="text-center">
            <span class = "textAnswer"> Придумывание длинных и сложных паролей, включая двуфакторную аутентификацию </span>
          </div>
        </div>
      </q-btn>
      <q-btn push class="button" :ripple="false" @click="selectOption('option1')">
        <div class="row items-center no-wrap" style="width: 100%;">
          <q-avatar size="42px" style="margin: 2px;">
            <img :src="selected === 'option1' ? option1Img : defaultImg">
          </q-avatar>
          <div class="text-center">
            <span class = "textAnswer"> Написание пароля на бумажке и сохранение её в кошельке </span>
          </div>
        </div>
      </q-btn>
      <q-btn push class="button" :ripple="false" @click="selectOption('option1')">
        <div class="row items-center no-wrap" style="width: 100%;">
          <q-avatar size="42px" style="margin: 2px;">
            <img :src="selected === 'option1' ? option1Img : defaultImg">
          </q-avatar>
          <div class="text-center">
            <span class = "textAnswer"> Рассказ пароля только лучшему другу </span>
          </div>
        </div>
      </q-btn>
    </div>
    <div v-if="showBlock" class="result-block">
      <q-chip class = "block" style = "margin-top: 25px !important; z-index: 2;" :ripple="false">
        <p class = "textGame" style="font-size: clamp(12px, 4vw, 20px); top: 5px;"> Сложные пароли содержат комбинацию букв, цифр и специальных символов, что делает их труднее подбираемыми для злоумышленников.</p>
      </q-chip>
      <q-btn push :ripple="false" flat style="right: -15px; position: absolute; bottom: -15px; background: #FAAA2E; border-radius: 250px; height: 75px;" href="/#/T1_2/">
        <div class="row items-center no-wrap">
          <q-avatar size="42px" style="margin: 2px;">
            <img src="~assets/next.svg" />
          </q-avatar>
        </div>
      </q-btn>
    </div>
  </q-page>
</template>

<script>
import { Global } from 'src/global';
import option1Img from 'src/assets/krest.svg';
import option2Img from 'src/assets/galka.svg';
import defaultImg from 'src/assets/elli.svg';
export default {
  data() {
    return {
      selected: null,
      showBlock: false,
      option1Img,
      option2Img,
      defaultImg,
      globalVariable: Global.variable
    };
  },
  methods: {
    methodAll(option) {
      this.selectOption(option);
      this.addOdin();
    },
    selectOption(option) {
      Global.variable = 0;
      console.log(this.globalVariable);
      this.selected = option;
      this.showBlock = true;
    },
    addOdin() {
      Global.variable = this.globalVariable + 1;
      this.globalVariable = Global.variable;
    }
  }
}
</script>

<style lang="scss" scoped>
@media screen and (max-height: 740px) and (max-width: 400px) {
  .textGame {
    font-size: 14px !important;
    line-height: 20px !important;
    bottom: -3px;
  }
  .block {
    height: 85px !important;
  }
  .img {
    scale: 3 !important;
  }
  .textAnswer {
    font-size: 14px !important;
  }
}
  .img {
    position: absolute;
    scale: 4;
    top: -60px;
    left: -5px;
  }
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
    color: #3A316A;
  }
  .button {
    background: #FAAA2E;
    left: 50%;
    transform: translate(-50%, 0);
    margin-top: 15px;
    max-width: 550px;
    width: 85%;
    border-radius: 30px;
  }
  .textAnswer {
    font-family: Roboto;
    color: #3A316A;
    text-transform: none;
    font-size: 20px;
    font-weight: 400;
  }
</style>