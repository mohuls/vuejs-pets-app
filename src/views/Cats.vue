<template>
  <div>
    <b-container>
      <h1>Cats for adoption</h1>
      <b-table striped hover :items="cats">
        <template #cell(name)="data">
          <router-link :to="`pets/cats/${data.index}`">
            {{ data.value }}
          </router-link>
        </template>
      </b-table>
    </b-container>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  data() {
    return {
    }
  },
  computed: {
    ...mapState([
      'cats'
    ])
  }
}
</script>