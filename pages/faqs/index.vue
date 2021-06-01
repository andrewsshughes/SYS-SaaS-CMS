<template>
  <div class="page-content">
    <Cliff :cliff="cliff" :small="true" />
    <Faqs :faq="faq" />
    <Cta :flip="true" />
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const pageContent = await $content('faqs').fetch()

    return {
      cliff: pageContent[0].cliff,
      faq: pageContent[0].faq,
    }
  },
}
</script>