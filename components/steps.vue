<template>
  <div class="steps">
    <div class="container">
      <div class="step" v-for="(step, index) in steps" :key="index">
        <div class="step-img-wrap">
          <img :src="step.icon" />
        </div>
        <div class="step-details">
          <span class="step-no">Step {{ index + 1 }}</span>
          <h2>{{ step.title }}</h2>
          <p v-for="(chunk, index) in formatDesc(step.desc, false)" :key="index">
            {{ chunk }}
          </p>
          <ul v-if="formatDesc(step.desc, true).length > 0">
            <li v-for="(item, index) in formatDesc(step.desc, true)" :key="index">
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
  props: ['steps'],
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
.steps {
  width: 80%;
  margin-left: auto;
  margin-right: auto;
}
.step {
  display: flex;
  padding: 20px 50px;
  box-sizing: border-box;
  width: 100%;
  gap: 10%;
  flex-direction: row-reverse;
  align-items: flex-start;
  position: relative;
}
.step:nth-of-type(2n) {
  margin-left: 0px;
  flex-direction: row;
}
.step > * {
  z-index: 3;
  position: relative;
}
.step-img-wrap {
  flex-basis: 45%;
}
.step-img-wrap img {
  width: 100%;
}
.step-details {
  flex-basis: 45%;
  padding-top: 21px;
}
.step-details h2 {
  color: #048dfd;
}
.step-details ul {
  padding-left: 20px;
}
.step-details .step-no {
  color: #ed0874;
  font-weight: 600;
}

.step:before {
  position: absolute;
  left: 20px;
  top: 46px;
  width: 9px;
  height: 9px;
  background: transparent;
  content: '';
  border-radius: 10px;
  background: #ed0874;
  box-shadow: 0px 0px 0px 3px rgba(237, 8, 116, 0.5);
  animation: spot 1000ms ease-in-out infinite;
  z-index: 4;
}
.step:nth-of-type(2n):before {
  left: calc(50% + 20px);
}
.step:after {
  position: absolute;
  width: 25%;
  height: calc(100% - 1px);
  content: '';
  left: 24px;
  border: 1px dashed rgba(0, 0, 0, 0.15);
  border-top-left-radius: 10px;
  border-bottom-left-radius: 10px;
  border-right: none;
  top: 0;
}
.step:nth-of-type(2n):after {
  top: 0;
  left: calc(25% + 24px);
  width: calc(25%);
  border-left: none;
  border-right: 1px dashed rgba(0, 0, 0, 0.15);
  border-top-left-radius: 0px;
  border-bottom-left-radius: 0px;
  border-top-right-radius: 10px;
  border-bottom-right-radius: 10px;
}
.step:first-of-type:after {
  border-top: 0;
  border-top-left-radius: 0px;
  top: 20px;
  height: calc(100% - 20px);
}
.step:last-of-type:after {
  border-bottom: 0;
  border-bottom-left-radius: 0px;
  border-bottom-right-radius: 0px;
  top: 0px;
  height: 100%;
}
@keyframes spot {
  0% {
    box-shadow: 0px 0px 0px 3px rgba(237, 8, 116, 0.5);
  }
  50% {
    box-shadow: 0px 0px 0px 0px rgba(237, 8, 116, 0.5);
  }
  100% {
    box-shadow: 0px 0px 0px 3px rgba(237, 8, 116, 0.5);
  }
}
</style>