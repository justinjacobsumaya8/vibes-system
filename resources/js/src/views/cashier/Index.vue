<template>
  <div class="p-m-4">
    <p class="text-2xl mb-6">Nav Bar</p>
    <v-row>
      <v-col cols="12">
        <card></card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import Card from './components/Card.vue'

export default {
  components: {
    Card,
  },
}
</script>

<style lang="scss" scoped>
.p-m-4 {
  padding: 8px;
  margin: 8px;
}
</style>
