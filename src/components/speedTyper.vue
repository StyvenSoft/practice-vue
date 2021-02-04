<template>
    <h1>Speed Typer</h1>
    <p>
        <span :key="keyword" v-for="keyword in keywords">
            {{ keyword }} {{ ' ' }}
        </span>
    </p>
    <input type="text" :value="inputValue" @keyup.space="processInput($event)"> 
</template>

<script>
export default {
    data() {
        return {
            inputValue: "",
            keywords: [
                'template', 
                'data', 
                'javascript', 
                'jquery',
                'vue',
                'vscode',
                'github',
                'ruby',
                'reactjs',
                'angular',
                'nextjs',
                'laravel'
            ]
        };
    },
    methods: {
        processInput(event) {
            const value = event.target.value.trim();
            if (value === "") {
                return;
            }
        }
    },
}
</script>


<style scoped>
</style>
