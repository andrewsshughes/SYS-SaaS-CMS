<template>
  <div class="cliff" :class="{ small: small == true }">
    <div class="cliff-fill-wrap">
      <div class="cliff-fill"></div>
    </div>
    <img class="break" src="/img/cliff-break.svg" />
    <div class="container">
      <div class="content">
        <h1>{{ cliff.title }}</h1>
        <p>{{ cliff.desc }}</p>
        <div class="btn-group" v-if="small != true">
          <div class="btn secondary"><i class="las la-phone"></i> Request a call</div>
          <div class="btn">Arrange a Demo</div>
        </div>
      </div>
    </div>
    <div class="preview-wrap" v-if="small != true">
      <div class="preview-img-wrap">
        <img
          v-for="(preview, index) in previews"
          :key="index"
          :src="preview"
          :class="{
            next: (index == 0 && currentPreview == previews.length - 1) || currentPreview + 1 == index,
            last: index + 1 == currentPreview || (currentPreview == 0 && index == previews.length - 1),
            active: index == currentPreview,
          }"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['cliff', 'small'],
  data: function () {
    return {
      currentPreview: 0,
      previews: [
        '/img/preview-screen-1.png',
        '/img/preview-screen-2.png',
        '/img/preview-screen-3.png',
        '/img/preview-screen-4.png',
        '/img/preview-screen-5.png',
      ],
    }
  },
  mounted() {
    setInterval(() => {
      this.currentPreview = this.currentPreview + 1
      this.currentPreview = this.currentPreview > this.previews.length - 1 ? 0 : this.currentPreview
    }, 5000)
  },
}
</script>

<style scoped>
.cliff {
  position: relative;
  background: red;
  height: 800px;
  padding-top: 150px;
  box-sizing: border-box;
  width: 100%;
  margin-bottom: 250px;
}
.cliff.small {
  height: 500px;
  margin-bottom: 100px;
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
.preview-img-wrap {
  max-width: 55%;
  position: relative;
  width: 55%;
  border-radius: 10px;
  box-shadow: 0 8px 16px 0 rgb(0 11 40 / 10%);
  border: 1px solid #f2f2f2;
  padding-top: 30.65%;
  overflow: hidden;
}
.preview-wrap img {
  object-fit: contain;
  width: 100%;
  position: absolute;
  left: 0;
  top: 0;
  height: auto;
  transition: 500ms ease-in-out;
  display: none;
}
.preview-wrap img.next {
  left: 100%;
  display: block;
}
.preview-wrap img.active {
  display: block;
}
.preview-wrap img.last {
  left: -100%;
  display: block;
}
@media screen and (max-width: 768px) {
  .cliff .content {
    width: 90%;
  }
  .cliff .content p {
    margin-bottom: 30px;
  }
  .preview-img-wrap {
    max-width: unset;
    width: 90%;
    padding-top: 50.65%;
  }
}
</style>