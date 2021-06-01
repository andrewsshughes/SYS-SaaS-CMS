<template>
  <div class="page-content">
    <Cliff :cliff="cliff" :small="true" />
    <Pricinglist :price="price" />
    <Cta :flip="true" />
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const pageContent = await $content('pricing').fetch()

    return {
      cliff: pageContent[0].cliff,
      price: pageContent[0].price,
    }
  },
}
</script>