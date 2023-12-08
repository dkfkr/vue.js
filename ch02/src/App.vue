<script>
export default {
  name: "App",
  data() {
    return {
      tit1: "Hello Vue",
      tit2: "Welcome Vue",
      tit3: "",
      result1: true,
      result2: false,
      score: 89,
      cities: ["서울", "대전", "대구", "부산", "광주"],
      persons: [
        { uid: "a101", name: "강감찬", age: 23 },
        { uid: "a102", name: "이순신", age: 25 },
        { uid: "a103", name: "유관순", age: 27 },
        { uid: "a104", name: "홍길동", age: 29 },
        { uid: "a105", name: "신사임당", age: 30 },
      ],
      value1: "tit1",
      value2: "tit2",
      count: 0,
      isActive: false,
      img1: "/img/flower3.jpg",
      img2: "/img/flower4.jpg",
      link1: "http://naver.com",
      link2: "http://google.com",
      style: { width: "100px", height: "100px", background: "orange" },
      myName: "홍길동",
      myTest: " ",
      myCheck: false,
      mycities: [],
      myUser: { uid: "", name: "", age: 0 },
    };
  },
  methods: {
    handler1() {
      alert("handler1");
    },

    handler2(value) {
      alert("handler2 : " + value);
    },

    handler3() {
      alert("handler3");
    },

    up() {
      this.count++;
    },

    changecity: function (e) {
      alert(e.target.value);
    },

    fromUser1(e) {
      const uid = e.target.elements.uid.value;
      const name = e.target.elements.name.value;
      const age = e.target.elements.age.value;

      console.log("uid : " + uid);
      console.log("name : " + name);
      console.log("age : " + age);
    },

    fromUser2(e) {
      console.log("uid : " + this.myUser.uid);
      console.log("name : " + this.myUser.name);
      console.log("age : " + this.myUser.age);
    },
  },
};
</script>

<template>
  <h3>Ch02. Vue Directive</h3>

  <h4>1) v-text</h4>
  <p v-text="tit1"></p>
  <p>{{ tit2 }}</p>

  <h4>2) v-show</h4>
  <p v-show="result1">show result1</p>
  <p v-show="result2">show result2</p>

  <h4>3) v-if</h4>
  <p v-if="result1">if result1</p>
  <p v-if="result2">if result2</p>
  <p v-else>else result2</p>

  <p v-if="score >= 90">A...</p>
  <p v-else-if="score >= 80">B...</p>
  <p v-else-if="score >= 70">C...</p>
  <p v-else-if="score >= 60">D...</p>
  <p v-else="score">F...</p>

  <p v-if="tit3">{{ tit3 }}</p>
  <p v-else>tit3 empty</p>

  <h4>4) v-for</h4>
  <ul>
    <li v-for="i in 3">i : {{ i }}</li>
  </ul>

  <ul>
    <li v-for="city in cities">{{ city }}</li>
  </ul>

  <table border="1">
    <tr>
      <th>uid</th>
      <th>name</th>
      <th>age</th>
    </tr>
    <tr v-for="person in persons">
      <th>{{ person.uid }}</th>
      <th>{{ person.name }}</th>
      <th>{{ person.age }}</th>
    </tr>
  </table>

  <h4>5) v-on</h4>
  <button v-on:click="handler1">button1</button>
  <button v-on:click="handler2(10)">button2</button>
  <button @click="handler3">button3</button>

  <p>count : {{ count }}</p>
  <button @click="up">UP</button><br />

  <select @change="changecity">
    <option>서울</option>
    <option>대전</option>
    <option>부산</option>
    <option>대구</option>
    <option>경주</option>
  </select>

  <form @:submit.prevent="fromUser1" method="post">
    uid : <input type="text" name="uid" /><br />
    name : <input type="text" name="name" /><br />
    age : <input type="text" name="age" /><br />
    <input type="submit" value="등록" />
  </form>

  <h4>6) v-bind</h4>
  <img v-bind:src="img1" />
  <img v-bind:src="img2" /><br />

  <a v-bind:href="link1">네이버</a><br />
  <a :href="link2">구글</a>

  <h4>7) v-model</h4>
  <p>name : {{ myName }}</p>
  <input type="text" placeholder="이름 입력" v-model="myName" />

  <p>{{ myName }}</p>
  <p>문자 갯수 : {{ myTest.length }}</p>
  <textarea v-model="myTest" cols="30" rows="10"></textarea>

  <p>
    <label><input type="checkbox" v-model="myCheck" />checkbox</label>
    체크상태: {{ myCheck }}
  </p>
  <p>
    {{ mycities }}<br />
    <label><input type="checkbox" v-model="mycities" value="서울" />서울</label>
    <label><input type="checkbox" v-model="mycities" value="대전" />대전</label>
    <label><input type="checkbox" v-model="mycities" value="대구" />대구</label>
    <label><input type="checkbox" v-model="mycities" value="포항" />포항</label>
    <label><input type="checkbox" v-model="mycities" value="광주" />광주</label>
  </p>

  <form @:submit.prevent="fromUser2" method="post">
    uid : <input type="text" v-model="myUser.uid" /><br />
    name : <input type="text" v-model="myUser.name" /><br />
    age : <input type="text" v-model="myUser.age" /><br />
    <input type="submit" value="등록" />
  </form>
</template>

<style scoped>
img {
  width: 100px;
  height: 100px;
}
</style>
