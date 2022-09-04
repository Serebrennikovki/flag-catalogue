<template>
  <div class="main" id='app'>
    <HeaderApp
    @openPopupRegistration = 'openPopupRegistration'/>
    <BreadCrumbs/>
    <CatalogueGoods/>
    <PopupRegistration 
    v-model:show="isVisiblePopupRegistration"/>
    <PopupConfirmation />
  </div>
</template>

<script>
import HeaderApp from './components/Header.vue';
import BreadCrumbs from '@/components/BreadCrumbs.vue';
import CatalogueGoods from '@/components/Catalogue.vue';
import PopupRegistration from '@/components/PopupRegistration.vue';
import PopupConfirmation from '@/components/PopupConfirmation.vue';
import '@/assets/fonts.css';

export default {
  name: 'App',
  components: {
    HeaderApp,
    BreadCrumbs,
    CatalogueGoods,
    PopupRegistration,
    PopupConfirmation
  },
  data(){
    return {isVisiblePopupRegistration:false}
  }, 
  methods:{
    openPopupRegistration(){
      console.log('app');
      this.isVisiblePopupRegistration = true;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
  .main{
    background-color: #E5E5E5;
    min-height: 100vh;
}
</style>
