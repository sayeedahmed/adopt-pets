<template>
  <div>
    {{ $route.params.id }}
    <h1>{{ currentAnimal.name }} ({{ $route.params.species }})</h1>
    <p>Age: {{ currentAnimal.age }} years old</p>
    <p>Breed: {{ currentAnimal.breed }}</p>
  </div>
</template>

<script>
// import cats from '@/data/cats'
import { mapState } from 'vuex'

export default {
  data () {
    return {
      currentAnimal: {}
    }
  },
  computed: {
    ...mapState([
      'cats',
      'dogs'
    ])
  },
  mounted () {
    const animal = this[this.$route.params.species][this.$route.params.id]
    this.currentAnimal = animal
  }
}
</script>
