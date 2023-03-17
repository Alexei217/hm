<script setup>
    import { reactive, ref, watchEffect } from 'vue';

    const counter = ref(0);
    const date = ref(new Date().toLocaleTimeString());
    function counterHeadler(event) {
        console.log();
        counter.value++;
    }

    watchEffect(() => {
        setInterval(() => {
            date.value = new Date().toLocaleTimeString();
        },1000);
});
</script>

<template>
   <button @click="counterHeadler">counter {{ counter }}</button>
   <h1>{{ date }}</h1>
   <button id="btn">Нажми</button>
</template>


<style lang="scss" scoped></style>