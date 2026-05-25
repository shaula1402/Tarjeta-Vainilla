<template>
   <NavBar />
  <section class="contacto">
    <h2>Contáctame</h2>
    <p>¿Tienes un proyecto en mente? Escríbeme y me pongo en contacto contigo.</p>

    <form @submit.prevent="enviarFormulario" class="form">
      <div class="campo">
        <label>Nombre</label>
        <input v-model="form.nombre" type="text" placeholder="Tu nombre completo" required />
      </div>
      <div class="campo">
        <label>Correo</label>
        <input v-model="form.correo" type="email" placeholder="tucorreo@ejemplo.com" required />
      </div>
      <div class="campo">
        <label>Teléfono</label>
        <input v-model="form.telefono" type="tel" placeholder="55 1234 5678" />
      </div>
      <div class="campo">
        <label>Proyecto</label>
        <textarea v-model="form.proyecto" placeholder="Cuéntame de tu proyecto..." rows="4" required />
      </div>

      <button type="submit" :disabled="enviando">
        {{ enviando ? 'Enviando...' : 'Enviar mensaje' }}
      </button>

      <p v-if="mensaje" :class="exito ? 'ok' : 'error'">{{ mensaje }}</p>
    </form>
  </section>
</template>

<script setup>
const APPS_SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbyUnkDOoaZGVUuC_r4_buIkf54dRHCYCKXyomGDChd8I4fpk5X3OMdZy6wN7Kfz4Dw5vg/exec'

const form = reactive({
  nombre: '',
  correo: '',
  telefono: '',
  proyecto: ''
})

const enviando = ref(false)
const mensaje = ref('')
const exito = ref(false)

async function enviarFormulario() {
  enviando.value = true
  mensaje.value = ''

  try {
    const formData = new FormData()
    formData.append('nombre', form.nombre)
    formData.append('correo', form.correo)
    formData.append('telefono', form.telefono)
    formData.append('proyecto', form.proyecto)

    await fetch(APPS_SCRIPT_URL, {
      method: 'POST',
      body: formData
    })

    exito.value = true
    mensaje.value = '✅ Mensaje enviado correctamente. Te contactaré pronto.'
    Object.assign(form, { nombre: '', correo: '', telefono: '', proyecto: '' })
  } catch (error) {
    console.error(error)
    exito.value = false
    mensaje.value = '❌ Hubo un error al enviar. Inténtalo de nuevo.'
  } finally {
    enviando.value = false
  }
}
</script>

<style scoped>
/* Tus estilos aquí */
.contacto {
  max-width: 600px;
  margin: 4rem auto;
  padding: 0 1.5rem;
}

.form {
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
}

.campo {
  display: flex;
  flex-direction: column;
  gap: 0.4rem;
}

input, textarea {
  padding: 0.8rem;
  border: 1px solid #333;
  border-radius: 6px;
  background: #1a1a1a;
  color: white;
}

button {
  background: white;
  color: black;
  padding: 0.9rem;
  border: none;
  border-radius: 6px;
  font-weight: 600;
  cursor: pointer;
}

.ok { color: #4caf50; }
.error { color: #f44336; }
</style>