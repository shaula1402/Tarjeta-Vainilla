<template>
  <div class="cv-container">
    <header>
      <div class="header-info">
        <h3>Ingeniera de Software / Enlace Administrativo</h3>

        <p class="bio">
          Soy un profesional apasionado por la optimización de procesos administrativos y el cumplimiento de metas institucionales, garantizando siempre la transparencia y la legalidad en la gestión tributaria.
        </p>

        <div class="contact-bar">
          <span>📞 +52 5614 7397 15</span>
          <span>✉️ diazshaula@gmail.com</span>
          <span>📍 EDOMEX, México</span>
        </div>
      </div>
    </header>

    <section class="programs-bar">
      <h2>PROGRAMAS</h2>
      <div class="skills-grid">
        <div class="skill"><span>Excel</span> <span class="dots">●●●●○</span></div>
        <div class="skill"><span>PowerPoint</span> <span class="dots">●●●●○</span></div>
        <div class="skill"><span>Word</span> <span class="dots">●●●○○</span></div>
        <div class="skill"><span>Photoshop</span> <span class="dots">●●●●○</span></div>
        <div class="skill"><span>Access</span> <span class="dots">●●●○○</span></div>
        <div class="skill"><span>Visual Studio Code</span> <span class="dots">●●○○○</span></div>
      </div>
    </section>

    <main>
      <section class="main-left">
        <h2>EXPERIENCIA PROFESIONAL</h2>
        <div class="job">
          <div class="job-meta">
            De 16/05/2025 a Actualidad <br> CDMX, México
          </div>
          <div class="job-details">
            <p class="company">SAT</p>
            <p class="role">Enlace</p>
            <p>
              Responsable de la gestión, seguimiento y control de procesos administrativos y fiscales, asegurando el cumplimiento de las metas institucionales y la correcta aplicación de la normatividad vigente (CFF y Miscelánea Fiscal).
            </p>
          </div>
        </div>

        <h2>REFERENCIAS</h2>
        <div class="references">
          <div>
            <strong>Raul Nagera Nava</strong><br>
            Empresa SAT | Cargo Jefe de Departamento<br>
            Tel: 5566 8832 52
          </div>
          <div>
            <strong>Sara Lopez Luna</strong><br>
            Empresa IMP | Cargo Subgerente<br>
            Tel: 5589 5712 07
          </div>
        </div>
      </section>

      <aside class="sidebar">
        <section>
          <h2>IDIOMAS</h2>
          <p>Español: Natal</p>
          <p>Inglés: Intermedio (B1/B2)</p>
        </section>

        <section>
          <h2>ESTUDIOS</h2>
          <div class="study-item">
            <p class="year">2021 - Actualidad</p>
            <p>
              <strong>Ingeniería en Sistemas</strong><br>
              Tecnológico Gustavo A. Madero<br>
              CDMX, México
            </p>
          </div>
        </section>
      </aside>
    </main>
  </div>
</template>

<script setup lang="ts">
// Lógica de Nuxt 3 aquí
</script>

<style scoped>
/* Aquí va todo tu CSS que ya tienes escrito abajo */
.cv-container {
  background-color: rgb(0, 0, 0);
  color: #ffffff;
  font-family: 'Fira Code', monospace;
  max-width: 980px;
  margin: 60px auto;
  padding: 2.5rem 2rem;
  border-radius: 15px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.8);
}

.programs-bar h2, .main-left h2 {
  color: #6e3ebb;
  border-bottom: 2px solid #6e3ebb;
  padding-bottom: 8px;
  margin-bottom: 1.2rem;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 12px;
}

.skill {
  display: flex;
  justify-content: space-between;
  background: rgba(255,255,255,0.05);
  padding: 10px 14px;
  border-radius: 8px;
}

main {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 2.5rem;
}

@media (max-width: 900px) {
  main { grid-template-columns: 1fr; }
}

.company {
  font-size: 1.25rem;
  font-weight: bold;
  color: #6e3ebb;
}

.references div {
  background: rgba(255,255,255,0.05);
  padding: 14px;
  border-radius: 8px;
  margin-bottom: 12px;
}
</style>