<template>
  <nav class="navbar">
    <div class="nav-brand">RUDRA</div>
    <ul class="nav-links">
      <li><NuxtLink to="/">Inicio</NuxtLink></li>
       <li><NuxtLink to="/contacto">Contacto</NuxtLink>
        <NuxtLink to="/proyectos">Portafolio</NuxtLink>
</li>
    </ul>
  </nav>
</template>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  background: #0f0f0f;
  border-bottom: 1px solid #2a2a2a;
  position: sticky;
  top: 0;
  z-index: 100;
}

.nav-brand {
  font-size: 1.4rem;
  font-weight: 700;
  color: #fff;
  letter-spacing: 2px;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 2rem;
  margin: 0;
  padding: 0;
}

.nav-links a {
  color: #aaa;
  text-decoration: none;
  font-size: 0.95rem;
  transition: color 0.2s;
}

.nav-links a:hover,
.nav-links a.router-link-active {
  color: #fff;
}
</style>