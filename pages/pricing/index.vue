<template>
  <div class="page-content">
    <Cliff :cliff="cliff" :small="true" />
    <Pricinglist :prices="prices" />
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const pageContent = await $content('pricing').fetch()

    return {
      cliff: pageContent[0].cliff,
      prices: pageContent[0].prices,
    }
  },
}
</script>