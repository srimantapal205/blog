<template>
  <div class="about">
    <h1>This is an about page</h1>
    <button type="button" @click="getData('Function Called')">SingleClick Button</button>
    <button type="button" @dblclick="getData('Function Called')">
      Double Click Button
    </button>
    <h2 @mousemove="getConsole()">Detected Mouse move event</h2>
    <h2>{{ changeValue }}</h2>
    <button @click="getIncrementValue">Increment Value</button>
    <button @click="getDicrementValue">Dicrement Value</button>
    <h2>Get Input fields value</h2>
    <input type="text" placeholder="Enter email" v-model="email" />
    <br />
    <br />
    <input type="password" placeholder="Enter Password" v-model="pass" />
    <br /><br />
    <button type="button" @click="getDataValue">Get Data</button>
    <h2>Get value from the checkbox and radio button</h2>
    <label for="java">Java </label
    ><input type="checkbox" name="" id="java" value="java" v-model="tehnology" />
    <label for="node">Node </label
    ><input type="checkbox" name="" id="node" value="node" v-model="tehnology" />
    <label for="php">PHP</label>
    <input type="checkbox" name="" id="php" value="php" v-model="tehnology" />
    <label for="net">.Net </label
    ><input type="checkbox" name="" id="net" value=".net" v-model="tehnology" />

    <p>Skills: {{ tehnology }}</p>
    <br /><br />
    <h2>Profession</h2>
    <label for="student">Student</label>
    <input
      type="radio"
      name="profession"
      value="student"
      id="student"
      v-model="profession"
    />
    <label for="developer">Developer</label>
    <input
      type="radio"
      name="profession"
      value="developer"
      id="developer"
      v-model="profession"
    />
    <p>I am a {{ profession }}</p>
    <h2>conditional rendering</h2>

    <p v-if="isShow">This is for First condition</p>
    <p v-else>This is for second condition</p>
    <button type="button" @click="isShow = !isShow">Click Condition</button>
    <h2>Apply for loop and make list</h2>

    <ul>
      <li v-for="(item, index) in setOfSkills" :key="index">
        {{ item }}
      </li>
      <div v-for="(item, index) in users" :key="index">
        <p>
          Name:<strong>{{ item.uname }}</strong
          >,
        </p>
        <p>Email:{{ item.email }}</p>
      </div>
    </ul>
  </div>
</template>

<script>
export default {
  name: "aboutPage",
  data() {
    return {
      changeValue: 0,
      email: null,
      pass: null,
      tehnology: [],
      profession: null,
      isShow: false,
      setOfSkills: [
        "Java",
        "HTML",
        "Javascript",
        "Vue Js",
        "JSON",
        "Node",
        "CSS",
        "SCSS",
      ],
      users: [
        { uname: "Sri", email: "sri@test.com" },
        { uname: "Mary", email: "mary@test.com" },
        { uname: "Sam", email: "sam@test.in" },
      ],
    };
  },
  methods: {
    conditionClick() {},
    getDataValue() {
      console.warn("Values :", this.email, this.pass);
    },

    getData(x) {
      alert(x);
    },
    getConsole() {
      console.log("mouse is moving");
    },
    getIncrementValue() {
      return this.changeValue++;
    },
    getDicrementValue() {
      return this.changeValue--;
    },
  },
};
</script>
