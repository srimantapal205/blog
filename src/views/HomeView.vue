<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
<div class="box" :class="adjustStyle">
<h1>This is VUE js Practice Code</h1>
</div>
<button class="changecolor" v-on:click="isRed=!isRed">Red Color</button>
    <ul>
      <li v-for="(item, index) in userLists" :key="index">
        <UserDetail :userData="item" :getName="getUserName" />
      </li>
    </ul>
    <h2>{{ email }}</h2>
    <P>{{ getName("Javascript") }}</P>
    <p>{{ getData() }}</p>
    <p>{{ getData().name }}</p>
    <p>{{ getData().email }}</p>
  </div>
  <h2>two way binding</h2>
  <input type="text" name="incValue" id="inc" v-model="count" />
  <h3>{{ count }}</h3>
  <h2>Pass Data to child Component</h2>
  <HelloWorld
    ref="childBlock"
    :cname="chName"
    :data="car"
    @someEvent="getPropsData"
    :getData="getPropsData"
  />
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import UserDetail from "@/components/UserDetail.vue";
export default {
  name: "HomeView",
  components: {
    HelloWorld,
    UserDetail,
  },
  computed: {
    adjustStyle() {
      return {
        red:this.isRed,
        green:this.isGreen
      }
    }
  },
  data() {
    return {
      isRed:true,
      isGreen:false,
      email: "test@test.com",
      count: 110,
      chName: "I am child component",
      car: { cename: "BMW", colors: "Red" },
      cars: [
        { carName: "BMW", color: "Red" },
        { carName: "Oddi", color: "Blue" },
      ],
      userLists: [
        { userName: "Sri", email: "sri@test.com" },
        { userName: "Sam", email: "sam@test.com" },
        { userName: "Peter", email: "ptr@test.com" },
        { userName: "Rock", email: "rok@test.com" },
        { userName: "Rishi", email: "rishi@test.com" },
      ],
    };
  },
  methods: {
    changeColor(){},
    getName(x) {
      return x;
    },
    getData() {
      return {
        name: "This is return Object",
        email: "return@test.in",
        email2: this.email,
      };
    },
    getPropsData() {
      alert("Function Called");
    },
    getUserName(name) {
      alert(name);
    },
  },
};
</script>
<style lang="scss">
  .box{
    width: 100%;
    min-height: 100px;
    border: 2px solid black;
    display: flexbox;
    flex-direction: column;
    align-items: center; color: black;
    justify-content: center;
    &.red{
    background-color: red;
    color: white;
  }
  &.green{
    background-color: green;
    color: white;
  }
  &.blue{
    background-color: blue;
    color: white;
  }
    h1{
      font-size: 46px;
 
    }
  }
  .changecolor{
    margin-top: 10px;
    height: 30px;
  }
  
</style>
