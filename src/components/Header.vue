<template>
  <div class="mainNavbar">
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <div class="navbar-brand">
        <a><span class="leasing">Leasing</span><span class="car">Car</span></a>
        <a class="leasingCompany"> | лизинговая компания</a>
        <div class="navbar-text">
          <a href="#" class="leasingLink" target="_blank">Лизинг</a>
          <a href="#" class="leasingLink" target="_blank">Каталог</a>
          <a href="#" class="leasingLink" target="_blank">О нас</a>
          <button @click="$emit('open')" type="button" class="btn btn-outline-warning">Оставить заявку</button>
        </div>
      </div>
    </nav>
    <div class="pos-f-t">
      <div class="collapse" id="navbarToggleExternalContent">
        <div class="bg-dark p-4">
          <h4 class="text-white">Collapsed content</h4>
          <span class="text-muted">Toggleable via the navbar brand.</span>
        </div>
      </div>
      <nav class="navbar navbar-dark bg-dark">
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarToggleExternalContent" aria-controls="navbarToggleExternalContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="burger navbar-toggler-icon"></span>
        </button>
      </nav>
    </div>
    <Form @open="openForm()" />
  </div>
  
</template>

<script>
import Form from '@/components/Form.vue'
export default {
  name: 'Header',
  components: {
    Form
  }
}
</script>
<style scoped>
  .mainNavbar {
    position: fixed;
    top: 0px;
    left: 0px;
    right: 0px;
    bottom: 0px;
    z-index: 1;
  }

  @media screen and (max-device-width: 500px) {
    .pos-f-t {
      display: block;
    }
  }
  @media screen and (min-device-width: 750px) {
    .pos-f-t {
      display: none;
    }
  }
  .burger {
    color: white;
  }
  .header {
    position: fixed;
    display:flex;
    width: 100%;
    height:125px;
    justify-content: space-between;
  }
  .zayavka {
    width:180px;
    height:30px;
    border: 2px solid orange;
    border-radius: 15%;
    
  }
  .zayavka p {
    color:orange;
  }
  .firstBlock {
    width:30%;
  }
  .secondBlock {
    display: flex;
    justify-content: space-between;
    width:50%;
  }
  @font-face {
    font-family: Nekst;
    src: url(../fonts/nekst/Nekst-Bold.otf);
  }
  @font-face {
    font-family: Gilroy;
    src: url(../fonts/gilroy/Gilroy-Black.ttf);
  }
  .leasingCompany {
    color:gray;
  }

  .leasing {
    color: orange;
    font-family: Gilroy;
    font-weight: bold;
    font-size: 24px;
  }
  .car {
    font-size: 24px;
    font-family: Gilroy;
    font-weight: bold;
    color:black;
  }
  .leasingLink {
    font-size: 14px;
    font-family: Nekst;
    font-weight: bold;
    color:black;
  }
</style>
