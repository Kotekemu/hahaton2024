<template>
  <q-layout view="HHH LPR FFF">
    <q-page-container class="main-container">
      <router-view />
    </q-page-container>
    <q-footer v-show="!$route.meta.hideFooBar" class="fixed-bottom footerBar">
      <FooterComponent />
    </q-footer>
  </q-layout>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
// import FooterComponent from 'src/components/FooterComponent.vue'
export default defineComponent({
  name: 'MainLayout',
  // components: { FooterComponent }
})
</script>

<style lang="scss" scoped>
.footerBar {
  width: 100%;
  height: 62px;
  background: #FFFFFF;
}
.main-container {
  padding: 0px;
  margin-bottom: 0px;
}
</style>