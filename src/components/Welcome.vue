<template>
    <div id="welcomeContainer">
        <span>Bienvenue !</span>
    </div>
</template>

<style scoped>
    div#welcomeContainer {
        width: 100%;
        height: 100%;
        color: white;
        position: relative;
    }

    span {
        font-size: 2rem;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translateY(-50%) translateX(-50%); 
    }

</style>

<script>

export default {
  name: 'Loader',

  components: {
  },

    data: () => ({
        show: false
    }),

    
  mounted:function(){
        this.show = true;
  }
};
</script>