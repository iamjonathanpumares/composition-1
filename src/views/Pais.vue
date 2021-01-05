<template>
  <h1>{{ nombre }}</h1>
  <p v-for="(pais, index) in arrayData" :key="index">
    {{ pais.name }} - {{ pais.region }}
  </p>
</template>

<script>
import { useFetch } from '../hooks/useFetch'

export default {
  props: ['nombre'],
  setup(props) {
    return { ...useFetch(`https://restcountries.eu/rest/v2/name/${props.nombre}`) }
  }
}
</script>