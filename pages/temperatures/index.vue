<template>
  <div class="container mx-auto flex flex-wrap justify-center items-stretch">
    <div class="w-full flex flex-col flex-wrap justify-center p-8 sm:pt-4">
      <temperature-table
        :temperatures="temperatures"
        description="Toutes les températures déjà relevées."
        title="Températures relevées"
        cta-link="/"
        cta-text="Partager ma mesure"
      />
    </div>
  </div>
</template>

<script>
import TemperatureTable from '~/components/TemperatureTable.vue'

export default {
  components: {
    TemperatureTable
  },
  async asyncData({ $axios }) {
    const {
      defaults: { baseURL }
    } = $axios
    const temperatures = await $axios.$get(
      baseURL + '/temperatures?_sort=id:DESC'
    )
    return { temperatures }
  }
}
</script>

<style></style>
