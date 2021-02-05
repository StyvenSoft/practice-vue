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

    <br><br>
    <input v-model="newCat">
    <button v-on:click="addKit" v-on:keyup.enter="addKit">+ Add</button>
    <ul>
        <li v-for="cat in cats" v-bind:key="cat">{{ cat.name.toUpperCase() }}</li>
    </ul>
</template>

<script>
export default {
    data() {
        return {
            greeting: "Hello ",
            count: 0,
            email: '',
            cats: [
                { name: 'Tom'},
                { name: 'Simba'},
                { name: 'Coco'},
                { name: 'Fenix'},
                { name: 'Nino'},
                { name: 'Romeo'},
            ],
            newCat: '',
        }
    },
    methods: {
    addKit: function() {
            this.cats.push({name: this.newCat})
            this.newCat = ''
        }
    },
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