<script setup>
  import { ref, onMounted, onUnmounted } from "vue";
  import style from "./Card.module.css";

  const discountDate = ref(Date.now());
  const interval = ref(0);

  onMounted(() => {
    interval.value = setInterval(() => (discountDate.value = Date.now()), 1000);
  });

  onUnmounted(() => {
    clearInterval(interval.value);
  });

  function DateToDiscount(date) {
    return Math.round((new Date(date).getSeconds() / 70) * 100);
  }     
</script>

<template>
  <div :class="style.card">
    <slot :discount="DateToDiscount(discountDate)"></slot>
  </div>
</template>