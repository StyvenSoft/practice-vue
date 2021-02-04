<template>
    <h1>Speed Typer</h1>
    <p>Your score: 
        {{ keywords.filter(keyword => keyword.correct).length }}
        / {{ keywords.length }}</p>
    <p>
        <span 
            :class="{ correct: keyword.correct, wrong: keyword.wrong, pending: keyword.pending }"
            :key="keyword.text" v-for="keyword in keywords">
            {{ keyword.text }} {{ ' ' }}
        </span>
    </p>
    <input type="text" :value="inputValue" @keyup.space="processInput($event)"> 
</template>

<script>

const defaultKeywords = [
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
            ].map(keywords => {
                return {
                    text: keywords,
                    correct: false,
                    wrong: false,
                    pending: true,
                }
            })
export default {
    data() {
        return {
            inputValue: "",
            index: 0,
            keywords: defaultKeywords,
        };
    },
    methods: {
        processInput(event) {
            const value = event.target.value.trim();
            if (value === "") {
                return;
            }

            if (this.keywords[this.index].text === value) {
                this.keywords[this.index].correct = true
                this.keywords[this.index].wrong = false
                this.keywords[this.index].pending = false
            } else {
                this.keywords[this.index].correct = false
                this.keywords[this.index].wrong = true
                this.keywords[this.index].pending = false
            }
            this.inputValue = "";
            this.index++;
        }
    },
}
</script>


<style scoped>

.pending {
    font-weight: bold;
}

.correct {
    font-weight: bold;
    color: green;
}

.wrong {
    font-weight: bold;
    color:red;
}

</style>
