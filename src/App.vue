<template>
  <v-app>
    <div id="app-container">
      <Loader v-if="!loaded"/>
      <transition name="fade" v-if="loaded">
        <Welcome v-if="showWelcome" style="position:absolute;"/>
      </transition>
      <transition name="fade" v-if="loaded">
        <MainContent v-if="showMainContent"/>
      </transition>
    </div>
  </v-app>
</template>

<style scoped>
  #app-container{
    background: rgba(0, 0, 0, 0) linear-gradient(45deg, rgb(106, 120, 209), rgb(0, 164, 189)) repeat scroll 0% 0%;
    height: 100%;
  }

  .fade-enter-active, .fade-leave-active {
      transition: opacity 2s; 
  }
  .fade-enter, .fade-leave-to {
      opacity: 0;
  }
</style>

<script>
import Loader from './components/Loader';
import Welcome from './components/Welcome';
import MainContent from './components/MainContent';

export default {
  name: 'App',

  components: {
    Loader,
    Welcome,
    MainContent
  },

  data: () => ({
    loaded: true,
    showWelcome: false,
    showMainContent: false
  }),
    
  mounted:function(){
    this.showWelcome = true;
    setTimeout(()=>{ this.showWelcome = false; }, 2000);
    setTimeout(()=>{ this.showMainContent = true; }, 3500);
  }
};
</script>
