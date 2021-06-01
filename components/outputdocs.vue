<template>
  <div class="output">
    <div class="container">
      <div class="output-docs">
        <h4>The Outputs</h4>
        <h2>Download Your Documents</h2>
        <p>Once you have completed steps 1 to 4, the system produces 4 key sets of documentation, these include:</p>
        <div class="document-list">
          <div class="doc" v-for="(doc, index) in docs" :key="index">
            <div class="doc-img-wrap">
              <img :src="doc.icon" />
            </div>
            <div class="doc-details">
              <span class="doc-sub">The Documents</span>
              <h2>Segmentation & Service Offering</h2>
              <p>
                Monocle ipsum dolor sit amet joy K-pop Tsutaya ryokan, Muji boutique elegant concierge first-class.
                Winkreative bespoke discerning bulletin international first-class remarkable perfect extraordinary
                classic carefully curated hub Baggu concierge.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['docs'],
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
        return paragraphs
      } else {
        return listItems
      }
    },
  },
}
</script>

<style scoped>
.output-docs {
  min-height: 50px;
  border: 1px dashed rgba(0, 0, 0, 0.15);
  text-align: center;
  padding: 25px;
  width: calc(90%);
  margin-left: auto;
  margin-right: auto;
}
.output {
  margin-bottom: 100px;
}
h2 {
  color: #048dfd;
}
h4 {
  color: #ed0874;
}
.output-docs > p {
  width: 50%;
  margin-left: auto;
  margin-right: auto;
}
.doc {
  display: flex;
  padding: 20px 50px;
  box-sizing: border-box;
  width: 100%;
  gap: 10%;
  flex-direction: row;
  align-items: flex-start;
  position: relative;
}
.doc:nth-of-type(2n) {
  margin-left: 0px;
  flex-direction: row-reverse;
}
.doc > * {
  z-index: 3;
  position: relative;
}
.doc-img-wrap {
  flex-basis: 45%;
}
.doc-img-wrap img {
  width: 100%;
}
.doc-details {
  flex-basis: 45%;
  padding-top: 21px;
  text-align: left;
}
.doc-details h2 {
  color: #048dfd;
}
.doc-details .doc-sub {
  color: #ed0874;
  font-weight: 600;
}
</style>