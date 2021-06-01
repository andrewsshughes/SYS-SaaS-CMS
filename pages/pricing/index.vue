<template>
  <div class="page-content">
    <Cliff :cliff="cliff" :small="true" />
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const pageContent = await $content('pricing').fetch()

    return {
      cliff: pageContent[0].cliff,
    }
  },
}
</script>