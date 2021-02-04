<template>
    <h1>{{ greeting }}</h1>
    <input v-model="greeting">

    <div v-if="count === 1">Green</div>
    <div v-else-if="count === 2">Red</div>
    <div v-else>Orange</div>

    <h2>Sing up</h2>
    <br>
    <input v-model="email"
           :class="[email.length < 2 ? 'orange' : 'green']">
    <br>
    <br>
    <button onclick="alert('Signed Up')"
            :disabled="email.length < 2"
    >Submit</button>

</template>

<script>
export default {
    data() {
        return {
            greeting: "Hello ",
            count: 0,
            email: '',
        }
    }
}
</script>

<style scoped>

input:focus {
    outline: none;
}

.orange {
    border: 2px solid orange;
}

.green {
    border: 2px solid green;
}
</style>