<template>
  <div class="pricing">
    <div class="container">
      <h2>{{ price.title }}</h2>
      <p>{{ price.desc }}</p>
      <div class="price-list">
        <div class="card" v-for="(price, index) in price.prices" :key="index">
          <div class="img-wrap">
            <img :src="price.image" />
          </div>
          <div class="contents">
            <div class="name-wrap">
              <h3>{{ price.name }}</h3>
            </div>
            <div class="price">
              <span class="value">£{{ price.price.toFixed(2) }}</span>
              <span v-if="price.type != 'Fixed Price'" class="freq">{{ price.type }}</span>
              <p v-for="(chunk, index) in formatDesc(price.desc, false)" :key="index">
                {{ chunk }}
              </p>
              <ul v-if="formatDesc(price.desc, true).length > 0">
                <li v-for="(item, index) in formatDesc(price.desc, true)" :key="index">
                  {{ item.substr(2, item.length - 2) }}
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['price'],
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
        return paragraphs.filter((i) => i.trim().length > 0)
      } else {
        return listItems.filter((i) => i.trim().length > 0)
      }
    },
  },
}
</script>

<style scoped>
.pricing {
  margin-bottom: 150px;
}
.pricing .container > h2 {
  text-align: center;
  margin-bottom: 25px;
  color: #048dfd;
}
.pricing .container > p {
  text-align: center;
  width: 80%;
  margin-left: 10%;
}
.price-list {
  display: flex;
  flex-direction: column;
}
.price-list .card {
  flex-basis: 30%;
  min-height: 50px;
  position: relative;
  border-radius: 4px;
  padding: 50px 20px;
  overflow: hidden;
  transition: 150ms ease-in;
  display: flex;
  gap: 10%;
}
.price-list .card:nth-child(2n + 1) {
  flex-direction: row-reverse;
}
.price-list .card .contents {
  flex-basis: 45%;
}
.card .name-wrap {
  color: #048dfd;
  text-align: center;
  display: block;
  margin-bottom: 20px;
  display: flex;
  justify-content: flex-start;
}
.card .img-wrap {
  flex-basis: 40%;
}
.card .img-wrap img {
  width: 100%;
}
.card .name-wrap h3 {
  font-size: 20px;
}
.card .price {
  font-size: 30px;
  font-weight: 600;
  color: #ed0874;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding-bottom: 20px;
  margin-bottom: 20px;
}
.card .price .freq {
  font-size: 10px;
  font-weight: 500;
}
.card p,
.card li {
  font-weight: 500;
  font-size: 14px;
  line-height: 22px;
  text-align: left;
  color: #242424;
  margin-bottom: 0;
}
.card ul {
  padding-left: 20px;
  margin-top: 0px;
}
</style>