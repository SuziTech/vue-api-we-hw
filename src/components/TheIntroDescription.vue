<template lang="html" <base href="/" />
  <div class="intro-description">
    <p>
      {{ msg }}
    </p>
  </div>
</template>

<script>
export default {
  TheIntroDescription: 'An introductory economics website that links GDP population and climate change',
  props: {
    msg: String
  }
}
</script>

<style lang="css" scoped>
</style>
