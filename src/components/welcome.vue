<template>
  <h1>Welcome</h1>
  <p>The static HTML</p>
  <p>My name is {{ myName }} i'm my profile is {{ profile }}</p>
</template>

<script>
const something = {
  data() {
    return {
      myName: "Steveen Echeverri",
      profile: "Developer",
    };
  },
  mounted() {
      this.myName = "Undefined"
      console.log(this.myName); // Undefined
  },
};

something.mounted() // This works in javascript

export default something
</script>

<style scoped>
</style>