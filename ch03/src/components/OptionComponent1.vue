<script>
export default {
  name: "OptionComponent1",

  data() {
    return {
      name: "K",
      age: 21,
      addr: "busan",
    };
  },
};
</script>

<template>
  <h4>data 옵션</h4>
  <p>
    name : {{ name }} <br />
    age : {{ age }} <br />
    addr : {{ addr }}
  </p>
</template>

<style scoped></style>
