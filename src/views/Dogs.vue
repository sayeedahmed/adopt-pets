<template>
  <div>
    <PetTable
      species="dogs"
      v-bind:pets="dogs"
    />
  </div>
</template>

<script>
// import dogs from '@/data/dogs'
import { mapState } from 'vuex'
import PetTable from '@/components/PetTable.vue'

export default {
  components: {
    PetTable
  },
  data () {
    return {}
  },
  computed: {
    ...mapState([
      'dogs'
    ])
  }
}
</script>

<style scoped>

</style>
