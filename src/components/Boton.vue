<template>
  <button @click="accionBoton">{{ textoBoton }}</button>
</template>

<script>
export default {
  props: ['textoBoton'],
  setup(props, context) {
    const accionBoton = () => {
      context.emit('accion')
    }

    return { accionBoton }
  }
}
</script>