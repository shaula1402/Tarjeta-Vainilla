<script setup>
const proyectos = [
  {
    nombre: 'Ajedrez 3D',
    github: 'https://github.com/shaula1402/tablero_ajedrez',
    vercel: 'https://tablero-ajedrez.vercel.app/'
   
  },
  {
    nombre: 'Figura 3D STL',
    github: 'https://github.com/shaula1402/Planeta3D/tree/main',
    vercel: 'https://planeta3-d-pearl.vercel.app/'
   
  },
  {
    nombre: 'Pagina API',
    github: 'https://github.com/tuusuario/spotify-clone',
    vercel: 'https://planeta3-d-pearl.vercel.app/'
   
  },
  {
    nombre: 'Desintegrador de Particulas',
    github: 'https://github.com/shaula1402/Particulas-',
    vercel: 'https://particulas-one.vercel.app/'
   
  }
]
</script>

<template>
  <div class="portafolio">
    <h1>Mi Portafolio</h1>

    <div class="grid">
      <div
        v-for="proyecto in proyectos"
        :key="proyecto.nombre"
        class="card"
      >
        <img :src="proyecto.imagen" :alt="proyecto.nombre" />

        <h2>{{ proyecto.nombre }}</h2>

        <p>{{ proyecto.descripcion }}</p>

        <div class="botones">
          <a :href="proyecto.github" target="_blank">
            GitHub
          </a>
          <a :href="proyecto.vercel" target="_blank">
            Vercel
          </a>

         
          
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.portafolio {
  padding: 40px;
  min-height: 100vh;
  background: #0f172a;
  color: white;
}

h1 {
  text-align: center;
  margin-bottom: 40px;
  font-size: 3rem;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 30px;
}

.card {
  background: #1e293b;
  border-radius: 20px;
  overflow: hidden;
  transition: 0.3s;
  box-shadow: 0 10px 25px rgba(0,0,0,0.3);
}

.card:hover {
  transform: translateY(-10px);
}

.card img {
  width: 100%;
  height: 220px;
  object-fit: cover;
}

.card h2 {
  padding: 20px 20px 10px;
}

.card p {
  padding: 0 20px 20px;
  color: #cbd5e1;
}

.botones {
  display: flex;
  gap: 10px;
  padding: 20px;
}

.botones a {
  flex: 1;
  text-align: center;
  padding: 12px;
  border-radius: 10px;
  text-decoration: none;
  background: #50C878;
  color: white;
  font-weight: bold;
  transition: 0.3s;
}

.botones a:hover {
  background: #3da861;
}
</style>