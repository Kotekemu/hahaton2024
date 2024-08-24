<template>
  <q-page style="background-color: black;">
    <video src="~assets/start.mp4" autoplay muted class = "video">
    </video>
    <PageTransition :show="showTransition" />
  </q-page>
</template>

<script type="text/javascript">
import { ref, onMounted } from 'vue';
import { useRouter } from 'vue-router';
import PageTransition from '../components/PageTransition.vue'; // Импортируйте компонент

export default {
  components: {
    PageTransition
  },
  setup() {
    const router = useRouter();
    const showTransition = ref(false);

    onMounted(() => {
      setTimeout(() => {
        showTransition.value = true;
        setTimeout(() => {
          router.push('/T1_1/');
        }, 500); // Время для завершения CSS анимации
      }, 3000); // Время до начала анимации
    });

    return {
      showTransition
    };
  }
}
</script>


<style lang="scss" scoped>
  .video {
    max-width: 100%;
    left: 50%;
    transform: translate(-50%, -50%);
    position: absolute;
    top: 50%;
  }
  .transition-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: black;
  opacity: 0;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}

.fade-enter, .fade-leave-to /* .fade-leave-active in <2.1.8 */ {
  opacity: 1;
}
</style>