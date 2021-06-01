<template>
  <div class="usps">
    <div class="container">
      <h2>Exclusively for SJP Partners</h2>
      <div class="usp-row">
        <div v-for="(usp, index) in usps" :key="index" class="usp">
          <div class="icon-wrap">
            <img class="blob bottom" src="/img/Blob.svg" />
            <img class="blob top" src="/img/Blob.svg" />
            <i :class="['las', `la-${usp.icon}`]" />
          </div>
          <h3>{{ usp.title }}</h3>
          <p>{{ usp.desc }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['usps'],
}
</script>

<style scoped>
.usps {
  margin-bottom: 100px;
}
h2 {
  text-align: center;
  margin-bottom: 25px;
  color: #048dfd;
}
.usp-row {
  display: flex;
  flex-direction: row;
  justify-content: center;
}
.usp {
  flex-basis: 33.33%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.usp .icon-wrap {
  position: relative;
  width: 80px;
  height: 80px;
  margin-bottom: 20px;
}
.usp .icon-wrap .blob {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  opacity: 0.5;
}
.usp .icon-wrap .blob.bottom {
  transform: rotate(115deg) scale(1.1);
}
.usp .icon-wrap .blob.top {
  transform: rotate(45deg) scale(1.1);
  opacity: 0.75;
}
.usp .icon-wrap i {
  position: absolute;
  left: 50%;
  top: 50%;
  font-size: 40px;
  transform: translate(-50%, -50%);
  color: white;
  padding-top: 3px;
}
.usp h3 {
  width: 75%;
  text-align: center;
  color: #ed0874;
}
.usp p {
  width: 80%;
  text-align: center;
}
</style>