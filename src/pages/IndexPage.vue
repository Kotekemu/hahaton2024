<template>
  <q-page style="background-color: black;">
    <video src="~assets/start.mp4" autoplay loop muted class = "video">
    </video>
  </q-page>
</template>

<script type="text/javascript">
  setTimeout('window.location="/#/game/"', 3000);
</script>


<style lang="scss" scoped>
  .video {
    max-width: 100%;
    left: 50%;
    transform: translate(-50%, -50%);
    position: absolute;
    top: 50%;
  }
</style>