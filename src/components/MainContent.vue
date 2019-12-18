<template>
    <div id="mainContentContainer">
        <Header/>
        <section>
          <!-- <Career/> -->
          <Projects/>
        </section>
    </div>
</template>

<style scoped>

  section{
    margin: 15px 0px;
  }
</style>

<script>
import Header from './Header';
//import Career from './Career';
import Projects from './Projects';

export default {
  name: 'MainContent',

  components: {
    Header,
    Projects,
    //Career
  }

};
</script>
