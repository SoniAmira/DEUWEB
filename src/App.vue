<template>
  <div id="app">
    <SocialsBar class="socialbar" />
    <router-view class="router-view-container"></router-view>
    <ScrollBtn class="socialbar" />
  </div>
</template>

<script>
import SocialsBar from "./components/SocialsBar.vue";
import ScrollBtn from "./components/ScrollBtn.vue";
export default {
  components: {
    SocialsBar,
    ScrollBtn,
  },
};
</script>

<style>
#app {
  text-align: center;
  color: #2c3e50;
  position: relative; /* Asegúrate de que el contenido esté posicionado relativamente */
  z-index: 1; /* Asegúrate de que el contenido esté por encima del fondo */
  overflow: hidden;
  font-size: 16px;
  line-height: 28px;
}

body {
  margin: 0;
  padding: 0;
  position: relative;
}

body::before {
  content: "";
  background-image: url("./assets/img/ucvreloj.png");
  background-size: 130%;
  background-position: center;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0.1; /* Ajusta la opacidad según tus necesidades */
  z-index: -1; /* Asegúrate de que el fondo esté detrás de todo el contenido */
}

.router-view-container {
  position: relative;
  z-index: 1; /* Asegúrate de que el contenido esté por encima del fondo */
}
.socialbar {
  position: relative;
  z-index: 2;
}
@media (max-width: 768px) {
  body::before {
    background-repeat: no-repeat;
    background-size: cover;
  }
}
</style>
