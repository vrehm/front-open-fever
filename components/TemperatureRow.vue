<template>
  <tr>
    <td class="px-6 py-4 whitespace-no-wrap border-b border-gray-200">
      <span
        class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-yellow-100 text-yellow-800"
      >
        {{ temperature.zipcode }}
      </span>
    </td>
    <td
      class="px-6 py-4 whitespace-no-wrap border-b border-gray-200 text-sm leading-5 text-gray-500"
    >
      {{ temperature.value }} °C
    </td>
    <td
      class="px-6 py-4 whitespace-no-wrap border-b border-gray-200 text-sm leading-5 text-gray-500"
    >
      {{
        $dateFns.format(temperature.created_at, 'dd/MM/yyyy', { locale: 'fr' })
      }}
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
</template>

<script>
export default {
  props: {
    temperature: {
      type: Object,
      required: true
    }
  }
}
</script>

<style></style>
