<template>
  <div class="footer">
    <div class="container">
      <div class="logo">
        <img src="/img/PlusGroupLogo.svg" />
      </div>
      <div class="comp-info">Plus Partner Services Limited, trading as Plus Group. VAT Number 191887360.</div>
      <div class="links">
        <router-link to="/">How it works</router-link>
        <router-link to="/pricing">Pricing</router-link>
        <router-link to="/faqs">FAQs</router-link>
      </div>
    </div>
  </div>
</template>

<style scoped>
.footer {
  padding: 20px;
  background: #f2f2f2;
  font-size: 12px;
}
.footer .container {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.footer img {
  height: 50px;
}
.links {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}
.links a {
  text-decoration: none;
  color: #242424;
  transition: 75ms ease-in;
}
.links a:hover {
  color: #ed0874;
}
@media screen and (max-width: 768px) {
  .footer .container {
    flex-direction: column;
    gap: 15px;
  }
  .footer > * {
    margin-bottom: 15px;
  }
  .footer .links {
    flex-direction: row;
    gap: 20px;
  }
  .footer .comp-info {
    text-align: center;
  }
}
</style>