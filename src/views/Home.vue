<template>
  <div class="home">
   <h1
    :style="{ color: color }"
   >Contador: {{ contador }}</h1>
   <button @click="aumentar">Aumentar</button>
   <button @click="disminuir">Disminuir</button>
  </div>
</template>

<script>

export default {
  data() {
    return {
      contador: 0
    }
  },
  computed: {
    color() {
      if (this.contador < 0) return 'red'
      return 'blue'
    }
  },
  methods: {
    aumentar() {
      this.contador++
    },
    disminuir() {
      this.contador--
    }
  }
}
</script>
