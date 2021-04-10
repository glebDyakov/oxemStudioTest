<template>
  <div v-if="formOpen">
    <span @click="closeForm()" class="material-icons">
      highlight_off
    </span>
    <h1>Онлайн-заявка</h1>
    <p>Заполните форму, и мы вскоре свяжемся с вами, чтобы</p>
    <p>ответить на вопросы</p>
   
   <form class="was-validated">
    <div class="mb-3">
      <input type="phone" id="inputPhone" class="form-control is-invalid3" placeholder="Телефон" aria-describedby="passwordHelpBlock" required>
      <div class="invalid-feedback">
        Правильно укажите телефон.
      </div>
    </div>
    <div class="mb-3">
      <input type="text" id="inputName" class="form-control is-invalid3" placeholder="Имя" aria-describedby="passwordHelpBlock" required>
      <div class="invalid-feedback">
        Правильно укажите имя.
      </div>
    </div>
  </form>

    <div class="shadowBox">
      <div class="shadow-sm p-3 mb-5 bg-white rounded">
        <span class="agreement">Нажимая на кнопку Оставить заявку я даю <br/>согласие </span><span class="personalData">на обработку персональных данных</span>
        <button @click="closeForm()" type="button" class="formButton btn btn-warning">Оставить заявку</button>  
      </div>
    </div>
    <br/>
    <div class="messenger messengerWhatsApp"></div>
    <div class="messenger messengerTelegram"></div>
  </div>
</template>

<script>
export default {
  name: 'Form',
  emits: [ 'open' ],
  methods:{
    closeForm(){
      this.formOpen = false;
    },
    openForm(){
      this.formOpen = true;
    }
  },
  data(){
    return {
      formOpen: false
    }
  }
}
</script>
<style scoped>
  .inputField {
    display:inline;
  }

  .shadowBox {
    width:100%;
    height:350px;
    display:flex;
    justify-content: center;
  }

  .messenger {
    float:left;
    width:50px;
    height:50px;
    border-radius: 100%;
  }
  .messengerWhatsApp {
    background-size:100% 100%;
    background-image:url('http://pngimg.com/uploads/whatsapp/whatsapp_PNG95151.png');
  }
  
  .messengerTelegram {
    background-size:100% 100%;
    background-image:url('https://www.pngkit.com/png/detail/897-8972864_telegram-telegram-logo-png.png');
  }

  .formButton {
    color:white;
    border-radius: 15px;
    font-weight:bold;
  }

  .personalData {
    color:black;
  }

  .agreement {
    color:gray;
  }
</style>