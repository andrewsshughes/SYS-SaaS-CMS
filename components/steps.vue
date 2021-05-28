<template>
  <div class="steps">
    <div class="container">
      <div class="step">
        <div class="border"></div>
        <div class="fill"></div>
        <div class="step-img-wrap">
          <img src="/img/Households.svg" />
        </div>
        <div class="step-details">
          <span class="step-no">Step 1</span>
          <h2>Create Your Segments</h2>
          <p>
            Monocle ipsum dolor sit amet joy K-pop Tsutaya ryokan, Muji boutique elegant concierge first-class.
            Winkreative bespoke discerning bulletin international first-class remarkable perfect extraordinary classic
            carefully curated hub Baggu concierge.
          </p>
          <p>
            First-class Boeing 787 lovely smart, Fast Lane Ettinger exclusive K-pop soft power sophisticated charming
            craftsmanship Washlet punctual business class. Global Sunspel emerging pintxos business class discerning,
            cosy premium hand-crafted Ginza destination exquisite Singapore. Sharp Comme des Garçons Tsutaya espresso.
          </p>
        </div>
      </div>
      <div class="step">
        <div class="border"></div>
        <div class="fill"></div>
        <div class="step-img-wrap">
          <img src="/img/Households.svg" />
        </div>
        <div class="step-details">
          <span class="step-no">Step 2</span>
          <h2>Create Your Segments</h2>
          <p>
            Monocle ipsum dolor sit amet joy K-pop Tsutaya ryokan, Muji boutique elegant concierge first-class.
            Winkreative bespoke discerning bulletin international first-class remarkable perfect extraordinary classic
            carefully curated hub Baggu concierge.
          </p>
          <p>
            First-class Boeing 787 lovely smart, Fast Lane Ettinger exclusive K-pop soft power sophisticated charming
            craftsmanship Washlet punctual business class. Global Sunspel emerging pintxos business class discerning,
            cosy premium hand-crafted Ginza destination exquisite Singapore. Sharp Comme des Garçons Tsutaya espresso.
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

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
  width: calc(100% - 5px);
  gap: 10%;
  flex-direction: row-reverse;
  align-items: center;
  position: relative;
  margin-bottom: 5px;
  margin-left: 5px;
}
.step:nth-of-type(2n) {
  margin-left: 0px;
  flex-direction: row;
}
.step:last-of-type {
  margin-bottom: 100px;
}
.step > * {
  z-index: 3;
  position: relative;
}
.step > .border {
  background: linear-gradient(45deg, #048dfd, #ed0874);
  width: calc(100% + 5px);
  position: absolute;
  height: calc(100% + 5px);
  z-index: 1;
  left: -5px;
  top: 0;
}
.step:nth-of-type(2n) > .border {
  left: 0px;
  top: 0px;
  background: linear-gradient(135deg, #048dfd, #ed0874);
}
.step:last-of-type > .border {
  height: 100%;
}
.step > .fill {
  background: white;
  width: 100%;
  height: 100%;
  position: absolute;
  left: 0;
  top: 0;
}
.step-img-wrap {
  flex-basis: 45%;
}
.step-img-wrap img {
  width: 100%;
}
.step-details {
  flex-basis: 45%;
}
.step-details h2 {
  color: #048dfd;
}
.step-details .step-no {
  color: #ed0874;
  font-weight: 600;
}
</style>