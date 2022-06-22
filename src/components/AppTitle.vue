<template>
  <h1 class="text-center d-print-none">{{ text }}</h1>
  <h1 class="text-center d-none d-print-block">Your Invoice</h1>
</template>

<script>
export default {
  props: {
    text: String,
  },
}
</script>

<style scoped>

</style>