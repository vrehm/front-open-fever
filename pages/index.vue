<template>
  <div class="container mx-auto flex flex-wrap justify-center items-stretch">
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
          for="code-postal"
          class="block text-sm leading-5 font-medium text-gray-700"
          >Code postal</label
        >
        <div class="mt-1 relative rounded-md shadow-sm">
          <input
            id="code-postal"
            class="form-input block w-full sm:text-sm sm:leading-5"
            placeholder="Entrez votre code postal (ex 75001)"
            type="number"
            step="100"
          />
        </div>
      </div>

      <div class="md:flex md:items-start">
        <temperature-share-button />
      </div>
    </div>
    <div class="w-full sm:w-1/2 flex flex-col flex-wrap justify-center px-1">
      <temperature-table />
    </div>
  </div>
</template>

<script>
import TemperatureShareButton from '~/components/TemperatureShareButton.vue'
import TemperatureTable from '~/components/TemperatureTable.vue'

export default {
  components: {
    TemperatureShareButton,
    TemperatureTable
  }
}
</script>

<style></style>
