<template>
  <div class="container mx-auto flex flex-wrap justify-center items-stretch">
    <div class="w-full flex flex-col flex-wrap justify-center p-8 sm:pt-4">
      <temperature-table
        :temperatures="temperatures"
        :description="description"
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
  async asyncData({ $axios, params }) {
    const {
      defaults: { baseURL }
    } = $axios
    const zipcode = params.zipcode
    const temperatures = await $axios.$get(
      baseURL + '/temperatures?zipcode_eq=' + zipcode
    )
    return { temperatures }
  },
  data() {
    return {
      description:
        'Toutes les températures déjà relevées sur ce code postal ' +
        this.$route.params.zipcode +
        '.'
    }
  }
}
</script>

<style></style>
