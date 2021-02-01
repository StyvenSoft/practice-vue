<template>
    <h1>Welcome</h1>
    <p>The static HTML</p>
    <p>My name is {{ myName }} i'm my profile is {{ profile }}</p>
</template>

<script>
export default {
    data() {
        return {
            myName: "Steveen Echeverri",
            profile: "Developer"
        }
    }
}
</script>

<style scoped>

</style>