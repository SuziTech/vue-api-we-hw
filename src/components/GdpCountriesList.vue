<template lang="html">
  <div id="gdpCountriesList">
    <ul>
      <list-component  v-for="(country, index) in gdpCountries" :country="country"
        :key="index">
      </list-component>
    </ul>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="css" scoped>
</style>
