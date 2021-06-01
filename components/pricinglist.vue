<template>
  <div class="pricing">
    <div class="container">
      <h2>Pricing to fit your requirements</h2>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur eu lorem ultricies, aliquet tortor eget,
        consequat leo. Curabitur malesuada nisl pulvinar mollis facilisis. Etiam dapibus a diam ut condimentum.
      </p>
      <div class="pricing-table">
        <div class="heading">
          <div>Product</div>
          <div>Fixed Price</div>
          <div>Per Household</div>
          <div>Per Client</div>
        </div>
        <div class="row" v-for="(price, index) in prices" :key="index">
          <div class="name">{{ price.name }}</div>
          <div class="price">{{ price.type == 'Fixed Price' ? `£${price.price.toFixed(2)}` : '-' }}</div>
          <div class="price">{{ price.type == 'Per Household' ? `£${price.price.toFixed(2)}` : '-' }}</div>
          <div class="price">{{ price.type == 'Per Client' ? `£${price.price.toFixed(2)}` : '-' }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['prices'],
}
</script>

<style scoped>
.pricing {
  margin-bottom: 150px;
}
h2 {
  text-align: center;
  margin-bottom: 25px;
  color: #048dfd;
}
p {
  text-align: center;
  width: 80%;
  margin-left: 10%;
}
.pricing-table {
  width: 80%;
  margin-left: 10%;
  margin-top: 50px;
}
.pricing-table .heading {
  font-size: 20px;
  font-weight: 600;
  display: flex;
  flex-direction: row;
  align-items: center;
}
.pricing-table .heading > div {
  flex-basis: 20%;
  text-align: center;
  background: #f2f2f2;
  color: #242424;
  padding: 30px 0;
}
.pricing-table .heading > div:nth-of-type(1) {
  flex-basis: 40%;
}
.pricing-table .heading > div:nth-of-type(2) {
  background: #048dfd;
  color: white;
}
.pricing-table .heading > div:nth-of-type(3) {
  background: #9066b5;
  color: white;
}
.pricing-table .heading > div:nth-of-type(4) {
  background: #ed0874;
  color: white;
}
.pricing-table .row {
  display: flex;
  flex-direction: row;
  align-items: center;
  background: #fdfdfd;
}
.pricing-table .row:nth-of-type(2n + 1) {
  background: #fbfbfb;
}
.pricing-table .row > div {
  flex-basis: 20%;
  text-align: center;
  color: #242424;
  padding: 30px 0;
  font-weight: 500;
}
.pricing-table .row .name {
  flex-basis: 40%;
  text-align: right;
  padding-right: 20px;
  box-sizing: border-box;
}
.pricing-table .row > div:nth-of-type(2) {
  background: rgba(4, 141, 253, 0.02);
}
.pricing-table .row > div:nth-of-type(3) {
  background: rgba(144, 102, 181, 0.02);
}
.pricing-table .row > div:nth-of-type(4) {
  background: rgba(237, 8, 116, 0.02);
}
</style>