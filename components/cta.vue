<template>
  <div class="cta" :class="{ flip: flip == true }">
    <div class="container">
      <div class="staff-image">
        <img src="/img/staff-placeholder.png" />
        <div class="details">
          <span class="name">Megan Bradshaw</span>
          <span class="jobrole">Client Servicing Manager</span>
        </div>
      </div>
      <div class="contents">
        <h2>Would you like a demonstration?</h2>
        <div class="btn-group">
          <a class="btn light heavy" href="https://meetings.hubspot.com/megan-bradshaw/1-hour-demo"
            >Click here to book</a
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['flip'],
}
</script>

<style scoped>
.cta {
  height: 250px;
  background: linear-gradient(90deg, #048dfd 0%, #ed0874 150%);
  margin-bottom: 100px;
}
.cta.cta.flip {
  margin-bottom: 0;
}
.cta .container {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: row;
}
.cta.flip .container {
  flex-direction: row-reverse;
}
.cta .staff-image {
  height: 250px;
  position: relative;
  width: 400px;
}
.cta .staff-image img {
  position: absolute;
  bottom: 0;
  width: 100%;
}
.cta .staff-image .details {
  position: absolute;
  bottom: 20px;
  left: 20px;
  color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.cta .staff-image .details .name {
  font-weight: 500;
  font-size: 18px;
}
.cta .staff-image .details .jobrole {
  font-size: 12px;
}
.cta .contents {
  text-align: center;
  margin-left: 25px;
}
.cta .contents h2 {
  color: white;
  margin-bottom: 20px;
}
@media screen and (max-width: 768px) {
  .cta .container {
    align-items: center;
    height: 100%;
  }
  .cta .container .contents {
    margin: 0;
  }
  .cta .staff-image {
    display: none;
  }
}
</style>