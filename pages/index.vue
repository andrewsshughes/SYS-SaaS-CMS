<template>
  <div class="page-content">
    <Cliff :cliff="cliff" />
    <Usp :usps="usps" />
    <Cta />
    <Steps :steps="steps" />
    <Outputdocs :docs="docs" />
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const pageContent = await $content('home').fetch()

    return {
      cliff: pageContent[0].cliff,
      usps: pageContent[0].usps,
      steps: pageContent[0].steps,
      docs: pageContent[0].docs,
    }
  },
}
</script>