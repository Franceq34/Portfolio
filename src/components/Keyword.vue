<template>
    <span class="tag">
        {{keyword.name}}
    </span>
</template>

<style scoped>
    span.tag{
        border-radius: 15px;
        color: #3c8bc8;
        background: #def1ff;
        padding: 4px 8px;
        margin-left: 3px;
        margin-right: 3px;
    }
    span.tag:first-child{
        margin-left: 0px;
    }
    span.tag:last-child{
        margin-right: 0px;
    }
</style>

<script>

export default {
  name: 'Keyword',
  props: ['keyword']
};
</script>