<template>
  <div class="header">
    <div class="container">
      <header>
        <div class="logo">
          <img src="/img/PlusGroupLogo.svg" />
        </div>
        <nav>
          <router-link to="/">How it works</router-link>
          <router-link to="/pricing">Pricing</router-link>
          <router-link to="/faqs">FAQs</router-link>
        </nav>
        <div class="cta-wrap">
          <a class="cta" href="https://meetings.hubspot.com/megan-bradshaw">
            <i class="las la-phone"></i>
            <span>Request a call</span>
          </a>
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
  filter: contrast(0) brightness(255);
}
nav {
  display: flex;
  color: white;
  justify-content: space-around;
  flex-basis: 33.33%;
  min-width: 500px;
}
nav a {
  cursor: pointer;
  text-align: center;
  position: relative;
  text-decoration: none;
  color: white;
}
nav a:before {
  height: 1px;
  width: 0;
  left: 50%;
  content: '';
  background: white;
  position: absolute;
  bottom: -2px;
  transition: 150ms ease-in;
}
nav a:hover:before {
  width: 100%;
  left: 0%;
}
.cta-wrap {
  flex-basis: 33.33%;
  flex-grow: 0;
  flex-shrink: 1;
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
  text-decoration: none;
}
.cta:hover {
  max-width: 165px;
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
@media screen and (max-width: 768px) {
  header {
    flex-direction: column;
    padding: 20px;
  }
  header .logo {
    margin-bottom: 20px;
  }
  nav {
    min-width: 350px;
  }
  header .cta {
    display: none;
  }
}
</style>