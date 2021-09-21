<template>
  <div class="page-content">
    <Cliff :cliff="cliff" :small="true" />
    <div class="container">
      <div class="terms">
        <p v-for="(chunk, index) in formatDesc(content, false)" :key="index" v-html="chunk"></p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const pageContent = await $content('terms').fetch()

    return {
      cliff: pageContent[0].cliff,
      content: pageContent[0].content,
    }
  },
  methods: {
    formatDesc(desc, list) {
      let chunks = desc.split(/\s\s/g)
      let listItems = []
      let paragraphs = []
      chunks.forEach((chunk, i) => {
        if (chunk.substr(0, 1) == '*') {
          listItems.push(chunk)
        } else {
          paragraphs.push(chunk)
        }
      })

      if (list != true) {
        paragraphs.forEach((p, i) => {
          let parts = p.split(' ')
          if (parts[0] == '#') {
            parts.splice(0, 1)
            p = parts.join(' ')
            paragraphs[i] = `<h3>${p}</h3>`
          } else if (parts[0] == '##') {
            parts.splice(0, 1)
            p = parts.join(' ')
            paragraphs[i] = `<h4>${p}</h4>`
          }
        })
        return paragraphs.filter((i) => i.trim().length > 0)
      } else {
        return listItems.filter((i) => i.trim().length > 0)
      }
    },
  },
}
</script>

<style>
.terms {
  padding-bottom: 100px;
}
.terms p {
  font-size: 16px;
}
.terms p h3 {
  color: #048dfd;
}
.terms p h4 {
  color: #ed0874;
}
</style>