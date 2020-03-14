<template>
  <div class="container mx-auto flex flex-wrap justify-center items-stretch">
    <add-temperature-notice v-if="showNotice" class="w-full absolute h-12" />

    <div
      id="temperature-form"
      class="w-full sm:w-1/2 flex flex-col flex-wrap justify-center px-1"
    >
      <div class="sm:max-w-xs mt-6">
        <label
          for="temperature"
          class="block text-sm leading-5 font-medium text-gray-700"
          >Température</label
        >
        <div class="mt-1 relative rounded-md shadow-sm">
          <input
            id="temperature"
            v-model.number="temperature"
            class="form-input block w-full sm:text-sm sm:leading-5"
            placeholder="0.00 °C (degrés Celsius)"
            type="number"
            step="0.01"
            min="0"
            max="50"
          />
        </div>
      </div>

      <div class="sm:max-w-xs my-6">
        <label
          for="zipcode"
          class="block text-sm leading-5 font-medium text-gray-700"
          >Code postal</label
        >
        <div class="mt-1 relative rounded-md shadow-sm">
          <input
            id="zipcode"
            v-model.number="zipcode"
            class="form-input block w-full sm:text-sm sm:leading-5"
            placeholder="Entrez votre code postal (ex 75001)"
            type="number"
            step="100"
          />
        </div>
      </div>

      <div class="md:flex md:items-start">
        <temperature-share-button @click.native="submitTemperature" />
      </div>
    </div>
    <div class="w-full sm:w-1/2 flex flex-col flex-wrap justify-center px-1">
      <temperature-table :temperatures="temperatures" />
    </div>
  </div>
</template>

<script>
import TemperatureShareButton from '~/components/TemperatureShareButton.vue'
import TemperatureTable from '~/components/TemperatureTable.vue'
import AddTemperatureNotice from '~/components/AddTemperatureNotice.vue'

export default {
  components: {
    AddTemperatureNotice,
    TemperatureShareButton,
    TemperatureTable
  },
  async asyncData({ $axios }) {
    const {
      defaults: { baseURL }
    } = $axios
    const temperatures = await $axios.$get(
      baseURL + '/temperatures?_sort=id:DESC&_limit=10'
    )
    return { temperatures }
  },
  data() {
    return {
      temperature: null,
      zipcode: null,
      showNotice: false
    }
  },
  methods: {
    async submitTemperature() {
      const {
        defaults: { baseURL }
      } = this.$axios
      const createTemperatureEndpoint = baseURL + '/temperatures/'
      const newTemperature = {
        value: this.temperature,
        zipcode: this.zipcode
      }
      await this.$axios
        .$post(createTemperatureEndpoint, newTemperature)
        .then((response) => {
          this.resetForm()
          this.refreshData()
        })
    },
    resetForm() {
      this.temperature = null
      this.zipcode = null
      this.showNotice = true
      this.startInterval(4000)
    },
    async refreshData() {
      const {
        defaults: { baseURL }
      } = this.$axios
      const temperatures = await this.$axios.$get(
        baseURL + '/temperatures?_sort=id:DESC&_limit=10'
      )
      this.temperatures = temperatures
    },
    startInterval(interval) {
      setInterval(() => {
        this.showNotice = false
      }, interval)
    }
  }
}
</script>

<style></style>
