<script setup>
    import style from "./App.module.css"; 
    import {ref} from "vue";
    import Card from "./components/Card/Card.vue";

    const input = ref("");
    const cards = ref([
        { model: "Mercedes"},
        { model: "BMW"},
        { model: "Honda"},
        { model: "Toyota"},
        { model: "Audi"},
        { model: "Ford"},
    ]);

    function getIsVisible(model) {
        return model.toLowerCase().includes(input.value.toLowerCase());
    }
    </script>


<template>
    <input v-model="input" :class="style.input" />
    <template v-for="({ model }, i) in cards">
        <Card v-if="getIsVisible(model)" v-slot="{ discount }">
            <h1>{{ model }}</h1>
            <p>discount: {{ discount + i }}%</p>
        </Card>
    </template>
</template>