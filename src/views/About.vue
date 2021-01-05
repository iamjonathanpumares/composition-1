<template>
  <div class="about">
    <Titulo :contador="contador" :color="color"/>
    <!-- <h1
      :style="{ color: color }"
    >Contador: {{ contador }}</h1> -->
    <!-- <button @click="aumentar">Aumentar</button>
    <button @click="disminuir">Disminuir</button> -->
    <Boton textoBoton="Aumentar" @accion="aumentar"/>
    <Boton textoBoton="Disminuir" @accion="disminuir"/>
    <hr>
    <input type="text" v-model="texto">
    <p>{{ texto }}</p>
  </div>
</template>

<script>
import { computed, ref } from 'vue'
import Titulo from '../components/Titulo'
import Boton from '../components/Boton'

export default {
  components: {
    Titulo,
    Boton
  },
  setup() {
    const contador = ref(0)
    const texto = ref('Contador')

    const aumentar = () => {
      contador.value++
    }

    const disminuir = () => {
      contador.value--
    }

    const color = computed(() => {
      if (contador.value < 0) return 'red'
      return 'blue'
    })

    return { contador, aumentar, disminuir, color, texto }
  }
}
</script>
