<template>
    <div id="mainContentContainer">
        <Header/>
        <Career/>
    </div>
</template>

<style scoped>

</style>

<script>
import Header from './Header';
import Career from './Career';

export default {
  name: 'MainContent',

  components: {
    Header,
    Career
  }

};
</script>
