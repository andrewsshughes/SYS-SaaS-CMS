<template>
  <div class="cliff">
    <div class="cliff-fill-wrap">
      <div class="cliff-fill"></div>
    </div>
    <img class="break" src="/img/cliff-break.svg" />
    <div class="container">
      <div class="content">
        <h1>{{ cliff.title }}</h1>
        <p>{{ cliff.desc }}</p>
        <div class="btn-group">
          <div class="btn secondary"><i class="las la-download"></i> Download Brochure</div>
          <div class="btn">Get in touch</div>
        </div>
      </div>
    </div>
    <div class="preview-wrap">
      <img src="/img/client-list-screen.png" />
    </div>
  </div>
</template>

<script>
export default {
  props: ['cliff'],
}
</script>

<style scoped>
.cliff {
  position: relative;
  background: red;
  height: 800px;
  padding-top: 200px;
  box-sizing: border-box;
  width: 100%;
  margin-bottom: 250px;
}
.cliff-fill-wrap {
  overflow: hidden;
  width: 100%;
  position: absolute;
  height: 100%;
  left: 0;
  top: 0;
}
.cliff-fill {
  width: 150%;
  background: linear-gradient(90deg, #048dfd, #ed0874);
  height: 100%;
  position: absolute;
  left: 0;
  top: 0;
  animation: cliff 5000ms infinite ease-in-out;
}
@keyframes cliff {
  0% {
    left: 0%;
  }
  50% {
    left: -50%;
  }
  100% {
    left: 0%;
  }
}
.cliff .break {
  bottom: -2px;
  left: 0;
  width: 100%;
  display: block;
  position: absolute;
}
.cliff .content {
  position: relative;
  z-index: 2;
  color: white;
  width: 60%;
  text-align: center;
  margin-left: auto;
  margin-right: auto;
}
.cliff .content p {
  font-size: 18px;
}
.preview-wrap {
  position: absolute;
  z-index: 50;
  top: 100%;
  transform: translate(-50%, -75%);
  display: flex;
  justify-content: center;
  width: 1440px;
  max-width: 100%;
  left: 50%;
}
.preview-wrap img {
  max-height: 600px;
  border-radius: 10px;
  box-shadow: 0 8px 16px 0 rgb(0 11 40 / 10%);
  border: 1px solid #f2f2f2;
  max-width: 55%;
  object-fit: contain;
}
</style>