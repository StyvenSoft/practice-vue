<template>
  <h1>Welcome</h1>
  <p>The static HTML</p>
  <p v-once>My name is {{ myName }} i'm my profile is {{ profile }}</p>
  <p>result sum: {{ 5 + 6 }}</p>
  <p>
    Conditional {{ 1 == 2 ? "Correct" : "Error" }}
    {{ Math.random() > 0.5 ? "True" : "False" }}
    {{ Math.sqrt(100) }}
  </p>
  <p v-html="rawHTML"></p>
  <h2>My favorite languages</h2>
  <ul>
    <li v-for="lang in proLanguages" v-bind:key="lang">
      {{ lang }}
    </li>
  </ul>
  <h2>My favorite Programs</h2>
  <ul>
    <li v-for="(pro, index) in programs" v-bind:key="pro.name">
      {{ index + 1 }} - {{ pro.name }}
    </li>
  </ul>
  <h2>Random number</h2>
  <p>
    Number: {{ randNumber }} <button v-on:click="aMehtod">Change Number</button>
  </p>

  <p>Create Number: {{ createNumber }}</p>
  <input :value="createNumber" @input="func($event)" />
  <!-- <input v-model="createNumber" /> -->
  <button @click="changeNum">Click change</button>

  <h1>Activities</h1>

  <p>{{ keywords.join(' | ') }}</p>
  <input :value="inputValue" @keyup.space="processInput($event)" />

</template>

<script>
// function somethingSum (a, b) {

// }

// somethingSum(10 > 20 ? 30 : 40, 20)
// somethingSum([1,2,3].map(t => t ** 2), 20)

export default {
  data() {
    return {
      myName: "Steveen Echeverri",
      profile: "Developer",
      rawHTML: "<strong>Template html</strong>",
      proLanguages: ["Javascript", "Python", "PHP", "C#", "Ruby"],
      programs: [
        {
          name: "Postman",
        },
        {
          name: "Visual Studio code",
        },
        {
          name: "NetBeans IDE",
        },
      ],
      randNumber: Math.random(),
      createNumber: 1,
      inputValue: "",
      index: 0,
      keywords: [],
    };
  },
  methods: {
    messageAlert() {
      alert("New message enabled");
    },
    aMehtod() {
      this.randNumber = Math.random();
      console.log("I was called");
    },
    func(e) {
      this.createNumber = e.target.value;
    },
    changeNum() {
      this.createNumber = 100;
    },
    processInput(event) {
        const value = event.target.value;
        this.keywords[this.index] = value;
        this.inputValue = "";
        this.index++;
    },
  },
  mounted() {
    //   this.myName = "Undefined"
    //   console.log(this.myName); // Undefined

    this.messageAlert();
  },
};
</script>

<style scoped>
ul {
  list-style: none;
}
</style>