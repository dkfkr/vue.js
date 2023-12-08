<script>
export default {
  name: "OptionComponent2",

  methods: {
    btnClick1() {
      alert("click1");
    },
    btnClick2() {
      alert("click2");
    },
    btnClick3() {
      alert("click3");
    },
  },
};
</script>

<template>
  <h4>methods 옵션</h4>
  <button @:click="btnClick1">button1</button>
  <button @:click="btnClick2">button2</button>
  <button @:click="btnClick3">button3</button>
</template>

<style scoped></style>
