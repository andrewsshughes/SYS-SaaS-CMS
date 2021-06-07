<template>
  <div class="faqs">
    <div class="container">
      <h2>{{ faq.title }}</h2>
      <p>{{ faq.desc }}</p>
      <div class="faqs-wrap">
        <div
          class="faq"
          v-for="(faq, index) in faq.faqs"
          :class="{ selected: index == selected }"
          :key="index"
          @click.stop.prevent="toggleSelect(index)"
        >
          <div class="faq-header">
            <span>{{ faq.question }}</span>
            <div class="icon">
              <i class="las la-question-circle" :class="{ hide: index == selected }"></i>
              <i class="las la-comment" :class="{ hide: index != selected }"></i>
            </div>
          </div>
          <div class="content">
            <p v-for="(chunk, index) in formatDesc(faq.answer, false)" :key="index">
              {{ chunk }}
            </p>
            <ul v-if="formatDesc(faq.answer, true).length > 0">
              <li v-for="(item, index) in formatDesc(faq.answer, true)" :key="index">
                {{ item.substr(2, item.length - 2) }}
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['faq'],
  data: function () {
    return {
      selected: null,
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
        return paragraphs
      } else {
        return listItems
      }
    },
    toggleSelect(index) {
      this.selected = index == this.selected ? null : index
    },
  },
}
</script>

<style scoped>
.faqs {
  margin-bottom: 150px;
}
.faqs .container > h2 {
  text-align: center;
  margin-bottom: 25px;
  color: #048dfd;
}
.faqs .container > p {
  text-align: center;
  width: 80%;
  margin-left: 10%;
}
.faqs .faqs-wrap {
  display: flex;
  flex-direction: column;
  width: 60%;
  margin-left: 20%;
  margin-top: 50px;
}
.faq {
  border-radius: 10px;
  box-shadow: 0 8px 16px 0 rgb(0 11 40 / 10%);
  padding: 20px;
  cursor: pointer;
  margin-bottom: 25px;
}
.faq .faq-header {
  font-weight: 600;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.faq .icon {
  position: relative;
  width: 40px;
  height: 40px;
}
.faq i {
  font-size: 32px;
  color: #048dfd;
  opacity: 1;
  position: absolute;
  transition: 250ms ease-in-out;
}
.faq i.hide {
  opacity: 0;
}
.faq .content {
  max-height: 0px;
  overflow: hidden;
  transition: 250ms ease-in-out;
}
.faq.selected .content {
  max-height: 300px;
  overflow: hidden;
}
.faq.selected {
  background: #e1f2ff;
  box-shadow: none;
}
.faq.selected i {
  color: white;
}
@media screen and (max-width: 768px) {
  .faqs .faqs-wrap {
    width: 90%;
    margin-left: 5%;
  }
  .faqs {
    margin-bottom: 20px;
  }
}
</style>