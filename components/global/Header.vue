<template>
  <div class="header">
    <div class="container">
      <header>
        <div class="logo">
          <img src="/img/PlusGroupLogo.svg" />
        </div>
        <nav>
          <span>How it works</span>
          <span>Pricing</span>
          <span>FAQs</span>
        </nav>
        <div class="cta-wrap">
          <div class="cta">
            <i class="las la-download"></i>
            <span>Download Brochure</span>
          </div>
        </div>
      </header>
    </div>
  </div>
</template>

<style scoped>
.header {
  position: absolute;
  background: rgba(255, 255, 255, 0);
  width: 100%;
  height: 75px;
  z-index: 5000;
}
header {
  width: 100%;
  display: flex;
  height: 100%;
  align-items: center;
  box-sizing: border-box;
  padding: 0px 25px;
  height: 75px;
}
header .logo {
  flex-basis: 33.33%;
}
header .logo img {
  height: 50px;
  filter: brightness(100);
}
nav {
  display: flex;
  color: white;
  justify-content: center;
  flex-basis: 33.33%;
}
nav span {
  margin-right: 50px;
  cursor: pointer;
  text-align: center;
  position: relative;
}
nav span:before {
  height: 1px;
  width: 0;
  left: 50%;
  content: '';
  background: white;
  position: absolute;
  bottom: -2px;
  transition: 150ms ease-in;
}
nav span:hover:before {
  width: 100%;
  left: 0%;
}
.cta-wrap {
  flex-basis: 33.33%;
  flex-grow: 0;
  flex-shrink: 0;
  display: flex;
  justify-content: flex-end;
}
.cta {
  display: flex;
  align-items: center;
  color: white;
  cursor: pointer;
  padding: 10px;
  box-sizing: border-box;
  max-width: 40px;
  transition: 150ms ease-out;
  overflow: hidden;
  background: rgba(255, 255, 255, 0);
  border-radius: 20px;
}
.cta:hover {
  max-width: 197px;
  background: rgba(255, 255, 255, 1);
  color: #242424;
}
.cta span {
  display: block;
  margin-left: 10px;
  width: 147px;
  min-width: 147px;
}
i {
  font-size: 20px;
}
</style>