<script setup>
    import style from "./App.module.css"; 
    import {ref} from "vue";
    const input = ref("");
    const cards = ref([
        { model: "Mercedes"},
        { model: "BMW"},
        { model: "Honda"},
        { model: "Toyota"},
        { model: "Audi"},
        { model: "Ford"},
    ]);
    </script>

<template>
    <input v-model="input" :class="style.input" />
    <template v-for="{ model } in cards">
        <div
            :class="style.card"
            v-if="model.toLowerCase().includes(input.toLowerCase())"
        >
            <h1>{{ model }}</h1>   
         </div>
    </template>
</template>