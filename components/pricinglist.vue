<template>
  <div class="pricing">
    <div class="container">
      <h2>{{ price.title }}</h2>
      <p>{{ price.desc }}</p>
      <div class="price-list">
        <div class="card" v-for="(price, index) in price.prices" :key="index">
          <div class="required" v-if="price.type == 'Fixed Price'">Required</div>
          <div class="name-wrap">
            <h3>{{ price.name }}</h3>
          </div>
          <div class="price">
            <span class="value">£{{ price.price.toFixed(2) }}</span>
            <span v-if="price.type != 'Fixed Price'" class="freq">{{ price.type }}</span>
          </div>
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
        return paragraphs
      } else {
        return listItems
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
  gap: 5%;
  margin-top: 150px;
}
.price-list .card {
  flex-basis: 30%;
  min-height: 50px;
  position: relative;
  border-radius: 4px;
  box-shadow: 0 8px 16px 0 rgb(0 11 40 / 10%);
  padding: 50px 20px;
  overflow: hidden;
}
.card .name-wrap {
  color: #048dfd;
  text-align: center;
  display: block;
  height: 50px;
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
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
  align-items: center;
  padding-bottom: 20px;
  margin-bottom: 20px;
  border-bottom: 1px solid #f2f2f2;
}
.card .price .freq {
  font-size: 10px;
  font-weight: 500;
}
.card p,
.card li {
  font-size: 12px;
  line-height: 14px;
  text-align: left;
  color: #242424;
}
.card ul {
  padding-left: 20px;
}
.card .required {
  position: absolute;
  height: 30px;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  background: linear-gradient(90deg, #048dfd, #0481e7);
  color: white;
  left: 0;
  top: 0;
}
</style>