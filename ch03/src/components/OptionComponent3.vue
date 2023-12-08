<script>
export default {
  name: "OptionComponent3",
  data() {
    return {
      price: 1000,
      count: 1,
      text: "",
      mycolor: "black",
    };
  },
  computed: {
    total() {
      return this.price * this.count;
    },
    textcount() {
      return this.text.length;
    },
    mscount() {
      return 20 - this.text.length;
    },
    comcolor() {
      this.mycolor = "green";

      if (this.mscount < 15) {
        this.mycolor = "orange";
      }

      if (this.mscount < 1) {
        this.mycolor = "red";
      }

      return this.mycolor;
    },
  },
};
</script>

<template>
  <h4>computed 옵션</h4>
  <div>
    <input type="number" v-model="price" /> 원
    <input type="number" v-model="count" /> 개수
    <p>금액 : {{ total }} 원</p>
  </div>

  <div>
    <p>20자 이내로 작성하십시오.</p>
    <textarea cols="30" rows="10" v-model="text"></textarea>
    <p>글자수 : {{ textcount }}</p>
    <p :style="{ color: comcolor }">남은 글자수 : {{ mscount }}</p>
  </div>
</template>

<style scoped>
textarea {
  resize: none;
}
</style>
