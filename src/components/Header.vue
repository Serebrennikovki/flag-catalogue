<script>
    export default {
    name: "HeaderApp",
    methods:{
        openPopup(){
            console.log('вызвали из хъдера');
            this.$emit('openPopupRegistration');
        }
    }
}
</script>

<template>
    <header class="header">
      <div class="header__container">
          <img class="logo" src="../assets/logo.svg" alt="Лого">
          <button type="button" class="button button__type_registry">
              <p class="button__text" @click="openPopup">Регистрация</p>
          </button>  
      </div> 
    </header>
</template>

<style scoped>
    .header{
    margin:0;
    background: #FFFFFF;
    box-shadow: 2px 4px 8px rgba(0, 0, 0, 0.1);
    display: flex;
    align-items: center;
    justify-content: center;
    height: 72px;
}
.header__container{
    margin:auto auto;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: baseline;
    width: 1208px;
}
.logo{
    margin:0px;
    width: 294px;
    height: 62px;
}
.button{
    border: none;
    margin:auto 0;
    padding: 8px;
    gap: 8px;
    width: 140px;
    height: 40px;
    background: #70C05B;
    border-radius: 4px; 
}
.button__text{
    color: #FFFFFF;
    margin:0;
    font-family: 'Rubik';
    font-weight: 400;
    font-size: 16px;
    line-height: 150%;
}
</style>