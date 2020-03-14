<template>
  <div>
    <div class="bg-white px-4 py-5 border-b border-gray-200 sm:px-6">
      <div
        class="-ml-4 -mt-4 flex justify-between items-center flex-wrap sm:flex-no-wrap"
      >
        <div class="ml-4 mt-4">
          <h3 class="text-lg leading-6 font-medium text-gray-900">
            Températures relevées
          </h3>
          <p class="mt-1 text-sm leading-5 text-gray-500">
            Table des températures transmises.
          </p>
        </div>
        <div class="ml-4 mt-4 flex-shrink-0">
          <span class="inline-flex rounded-md shadow-sm">
            <nuxt-link to="/temperatures">
              <button
                type="button"
                class="relative inline-flex items-center px-4 py-2 border border-transparent text-sm leading-5 font-medium rounded-md text-white bg-blue-600 hover:bg-blue-500 focus:outline-none focus:shadow-outline-blue focus:border-blue-700 active:bg-blue-700"
              >
                Voir toutes les températures
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
              <tr>
                <td
                  class="px-6 py-4 whitespace-no-wrap border-b border-gray-200"
                >
                  <span
                    class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-green-100 text-green-800"
                  >
                    69002
                  </span>
                </td>
                <td
                  class="px-6 py-4 whitespace-no-wrap border-b border-gray-200 text-sm leading-5 text-gray-500"
                >
                  37.5 °C
                </td>
                <td
                  class="px-6 py-4 whitespace-no-wrap border-b border-gray-200 text-sm leading-5 text-gray-500"
                >
                  14/03/20
                </td>
                <td
                  class="hidden md:table-cell px-6 py-4 whitespace-no-wrap text-right border-b border-gray-200 text-sm leading-5 font-medium"
                >
                  <a
                    href="#"
                    class="text-blue-600 hover:text-blue-900 focus:outline-none focus:underline"
                    >Filtrer par ce code</a
                  >
                </td>
              </tr>
              <tr>
                <td
                  class="px-6 py-4 whitespace-no-wrap border-b border-gray-200"
                >
                  <span
                    class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-green-100 text-green-800"
                  >
                    69002
                  </span>
                </td>
                <td
                  class="px-6 py-4 whitespace-no-wrap border-b border-gray-200 text-sm leading-5 text-gray-500"
                >
                  37.5 °C
                </td>
                <td
                  class="px-6 py-4 whitespace-no-wrap border-b border-gray-200 text-sm leading-5 text-gray-500"
                >
                  14/03/20
                </td>
                <td
                  class="hidden md:table-cell px-6 py-4 whitespace-no-wrap text-right border-b border-gray-200 text-sm leading-5 font-medium"
                >
                  <a
                    href="#"
                    class="text-blue-600 hover:text-blue-900 focus:outline-none focus:underline"
                    >Filtrer par ce code</a
                  >
                </td>
              </tr>
              <tr>
                <td
                  class="px-6 py-4 whitespace-no-wrap border-b border-gray-200"
                >
                  <span
                    class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-green-100 text-green-800"
                  >
                    75001
                  </span>
                </td>
                <td
                  class="px-6 py-4 whitespace-no-wrap border-b border-gray-200 text-sm leading-5 text-gray-500"
                >
                  37.5 °C
                </td>
                <td
                  class="px-6 py-4 whitespace-no-wrap border-b border-gray-200 text-sm leading-5 text-gray-500"
                >
                  14/03/20
                </td>
                <td
                  class="hidden md:table-cell px-6 py-4 whitespace-no-wrap text-right border-b border-gray-200 text-sm leading-5 font-medium"
                >
                  <a
                    href="#"
                    class="text-blue-600 hover:text-blue-900 focus:outline-none focus:underline"
                    >Filtrer par ce code</a
                  >
                </td>
              </tr>
              <tr>
                <td class="px-6 py-4 whitespace-no-wrap">
                  <span
                    class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-green-100 text-green-800"
                  >
                    75001
                  </span>
                </td>
                <td
                  class="px-6 py-4 whitespace-no-wrap text-sm leading-5 text-gray-500"
                >
                  37.5 °C
                </td>
                <td
                  class="px-6 py-4 whitespace-no-wrap border-b border-gray-200 text-sm leading-5 text-gray-500"
                >
                  14/03/20
                </td>
                <td
                  class="hidden md:table-cell px-6 py-4 whitespace-no-wrap text-right text-sm leading-5 font-medium"
                >
                  <a
                    href="#"
                    class="text-blue-600 hover:text-blue-900 focus:outline-none focus:underline"
                    >Filtrer par ce code</a
                  >
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style></style>
