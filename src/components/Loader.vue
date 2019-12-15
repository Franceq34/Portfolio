<template>
    <div>
        loading ...
    </div>
</template>

<style scoped>
    div {
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

    .fade-enter-active, .fade-leave-active {
        transition: opacity 5s; 
    }
    .fade-enter, .fade-leave-to {
        opacity: 0;
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