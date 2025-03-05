<template>
  <div>
    <button class="scroll-to-top" @click="scrollToTop">⮝</button>
  </div>
</template>

<script>
export default {
  methods: {
    scrollToTop() {
      window.scrollTo({ top: 0, behavior: "smooth" });
    },
  },
};
</script>

<style scoped>
.scroll-to-top {
  position: fixed;
  right: 20px; /* Coloca el botón en el costado derecho */
  bottom: 20px; /* Colócalo 20px desde la parte inferior */
  width: 60px;
  height: 60px;
  background-color: #01695b;
  color: white;
  border-radius: 50%; /* Hace que el botón sea circular */
  font-size: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  border: none;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: background-color 0.3s, transform 0.3s;
}

.scroll-to-top:hover {
  background-color: #014d43;
  transform: scale(1.1); /* Efecto de agrandar al hacer hover */
}

.scroll-to-top:focus {
  outline: none; /* Eliminar el borde de enfoque */
}
</style>
