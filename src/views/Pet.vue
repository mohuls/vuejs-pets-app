<template>
    <div>
       <h1>{{ animal.name }} ({{ $route.params.species }})</h1>
       <p> {{ animal.age }} years old</p>
       <p> {{ animal.notes }}</p>
    </div>
</template>

<script>
import { mapState } from "vuex"
export default {
  data() {
    return {
        animal: ''
    }
  },
  computed: {
    // cats() {
    //     return this.$store.state.cats
    // },
    // dogs() {
    //     return this.$store.state.dogs
    // }
    // same as the below shorthand
    ...mapState([
        'dogs',
        'cats'
    ])
},
mounted() {
    const animal = this[this.$route.params.species][this.$route.params.id]
    this.animal = animal
    }
}
</script>