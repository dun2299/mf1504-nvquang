<template>
    <button id="add" class="m-btn">{{text}}</button>
</template>

<script>

export default {
    name:"MButton",
    props: {
        text: String,
    }
}
</script>

<style scoped>
@import url(../../css/components/button.css);
</style>