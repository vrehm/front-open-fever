<template>
  <div>
    <div class="bg-white px-4 py-5 border-b border-gray-200 sm:px-6">
      <div
        class="-ml-4 -mt-4 flex justify-between items-center flex-wrap sm:flex-no-wrap"
      >
        <div class="ml-4 mt-4">
          <h3 class="text-lg leading-6 font-medium text-gray-900">
            {{ title }}
          </h3>
          <p class="mt-1 text-sm leading-5 text-gray-500">
            {{ description }}
          </p>
        </div>
        <div class="ml-4 mt-4 flex-shrink-0">
          <span class="inline-flex rounded-md shadow-sm">
            <nuxt-link :to="ctaLink">
              <button
                type="button"
                class="relative inline-flex items-center px-4 py-2 border border-transparent text-sm leading-5 font-medium rounded-md text-white bg-blue-600 hover:bg-blue-500 focus:outline-none focus:shadow-outline-blue focus:border-blue-700 active:bg-blue-700"
              >
                {{ ctaText }}
              </button>
            </nuxt-link>
          </span>
        </div>
      </div>
    </div>

    <div class="flex flex-col mt-6">
      <div class="-my-2 py-2 overflow-x-auto sm:-mx-6 sm:px-6 lg:-mx-8 lg:px-8">
        <div
          class="align-middle inline-block min-w-full shadow overflow-hidden sm:rounded-lg border-b border-gray-200"
        >
          <table class="min-w-full">
            <thead>
              <tr>
                <th
                  class="px-6 py-3 border-b border-gray-200 bg-gray-50 text-left text-xs leading-4 font-medium text-gray-500 uppercase tracking-wider"
                >
                  Code postal
                </th>
                <th
                  class="px-6 py-3 border-b border-gray-200 bg-gray-50 text-left text-xs leading-4 font-medium text-gray-500 uppercase tracking-wider"
                >
                  Température
                </th>
                <th
                  class="px-6 py-3 border-b border-gray-200 bg-gray-50 text-left text-xs leading-4 font-medium text-gray-500 uppercase tracking-wider"
                >
                  Date
                </th>
                <th
                  class="hidden md:table-cell px-6 py-3 border-b border-gray-200 bg-gray-50"
                ></th>
              </tr>
            </thead>

            <tbody class="bg-white">
              <temperature-row
                v-for="temperature in temperatures"
                :key="temperature.id"
                :temperature="temperature"
              />
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TemperatureRow from '~/components/TemperatureRow.vue'

export default {
  components: {
    TemperatureRow
  },
  props: {
    temperatures: {
      type: Array,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    ctaLink: {
      type: String,
      required: true
    },
    ctaText: {
      type: String,
      required: true
    }
  }
}
</script>

<style></style>
