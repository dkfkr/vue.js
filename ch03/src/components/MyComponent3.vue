<style scoped>
h3 {
  color: green;
}
</style>

<script>
import MyComponent4 from "./MyComponent4.vue";

export default {
  name: "MyComponent3",
  components: {
    MyComponent4,
  },
};
</script>

<template>
  <h3>My Component3</h3>
  <p>부모 컴포넌트</p>
  <MyComponent4 />
</template>
