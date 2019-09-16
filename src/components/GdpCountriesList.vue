<template lang="html">
  <div id="gdpCountriesList">
    <ul>
      <p  v-for="(country, index) in gdpCountries" :country="country"
        :key="index">{{ country["Country Name"] }}
      </p>
    </ul>
  </div>
</template>

<script>
export default {
  props: ['gdpCountries']
}
</script>

<style lang="css" scoped>
</style>
