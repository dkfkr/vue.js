<script setup>
import MyComponent1 from "./components/MyComponent1.vue";
import MyComponent2 from "./components/MyComponent2.vue";
import MyComponent3 from "./components/MyComponent3.vue";
import OptionComponent1 from "./components/OptionComponent1.vue";
import OptionComponent2 from "./components/OptionComponent2.vue";
import OptionComponent3 from "./components/OptionComponent3.vue";
</script>

<template>
  <h3>ch03 컴포넌트</h3>

  <h4>1) 컴포넌트</h4>
  <MyComponent1 />
  <MyComponent2 />
  <MyComponent3 />

  <h4>2) Option API</h4>
  <OptionComponent1 />
  <OptionComponent2 />
  <OptionComponent3 />

  <h4>3) 컴포넌트 통신</h4>

  <h4>4) 컴포넌트 생명주기</h4>
</template>

<style scoped></style>
