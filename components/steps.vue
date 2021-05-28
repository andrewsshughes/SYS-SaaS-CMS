<template>
  <div class="steps">
    <div class="container">
      <div class="step">
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
      <div class="step">
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
  width: 100%;
  gap: 10%;
  flex-direction: row-reverse;
  align-items: center;
  position: relative;
}
.step.step.no-fill {
  padding: 10px 50px;
  flex-direction: column;
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

.step:before {
  position: absolute;
  left: 20px;
  top: 20px;
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
  position: absolute;
  left: calc(50% + 20px);
  top: 20px;
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
}
.step:nth-of-type(2n):after {
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