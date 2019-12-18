<template>
    <div class="projectLink">
        <img :src="link.icon"/>
        <div>{{link.name}}</div>
    </div>
</template>

<style scoped>

    .projectLink {
        flex-direction: row;
        display: flex;
        margin: 0px 5px;
    }
    .projectLink img {
        width: 16px;
    }
    .projectLink div {
        line-height: 16px;
        margin-left: 5px;
        font-size: 0.8rem;
    }
</style>

<script>

export default {
  name: 'ProjectLink',   
  props: ['link']
};
</script>