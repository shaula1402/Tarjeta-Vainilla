<template>
  <div class="background"></div>
</template>

<script setup>
// No necesitas lógica
</script>

<style scoped>
.background {
  position: fixed;
  inset: 0;
  z-index: -1;
  pointer-events: none;
  overflow: hidden;

  /* 🎨 Fondo base */
  background-color: #0a0a0f;

  /* 🌌 Capas múltiples (gradientes + puntos + glow) */
  background-image:
    /* Glow verde (arriba izquierda) */
    radial-gradient(circle at 20% 10%, rgba(80, 200, 120, 0.25), transparent 40%),

    /* Glow verde (abajo derecha) */
    radial-gradient(circle at 80% 90%, rgba(80, 200, 120, 0.2), transparent 40%),

    /* Puntos tipo grid */
    radial-gradient(rgba(255,255,255,0.08) 1px, transparent 1px),

    /* Sombra oscura suave */
    linear-gradient(180deg, rgba(0,0,0,0.6), rgba(0,0,0,0.9));

  /* 📏 Tamaños de cada capa */
  background-size:
    600px 600px,
    600px 600px,
    25px 25px,
    100% 100%;

  background-repeat: no-repeat, no-repeat, repeat, no-repeat;

  /* ✨ Animación ligera */
  animation: moveBg 20s linear infinite;
}

/* 🌊 Movimiento sutil */
@keyframes moveBg {
  0% {
    background-position:
      20% 10%,
      80% 90%,
      0 0,
      0 0;
  }
  100% {
    background-position:
      25% 15%,
      75% 85%,
      25px 25px,
      0 0;
  }
}
</style>