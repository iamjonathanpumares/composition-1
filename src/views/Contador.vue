<template>
  <h1>Contador: {{ contador }}</h1>
  <Boton textoBoton="Aumentar" @accion="aumentar"/>
  <Boton textoBoton="Disminuir" @accion="disminuir"/>
</template>

<script>
import { useContador } from '../hooks/useContador'
import Boton from '../components/Boton'

export default {
  components: {
    Boton,
  },
  setup() {
    const { contador, aumentar, disminuir } = useContador()
    return { contador, aumentar, disminuir }
    return { ...useContador() }
  }
}
</script>