<template>
  <h1>Welcome</h1>
  <p>The static HTML</p>
  <p v-once>My name is {{ myName }} i'm my profile is {{ profile }}</p>
  <p>result sum: {{ 5 + 6 }}</p>
  <p>Conditional {{ 1 == 2 ? 'Correct' : 'Error'}} 
      {{ Math.random() > 0.5 ? 'True' : 'False'}}
      {{ Math.sqrt(100) }}
  </p>
  <p v-html="rawHTML"></p>
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
    };
  },
  methods: {
      messageAlert() {
          alert("New message enabled");
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
</style>