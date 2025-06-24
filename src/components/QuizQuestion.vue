<template>
    <div class="question">
        <h2>{{ props.question.text }}</h2>

        <ul>
            <li v-for="(option, index) in props.question.options" :key="index" @click="selectOption(option)">
                <strong>{{ option.label }}:</strong> {{ option.text }}
            </li>
        </ul>
    </div>
</template>

<script setup>
// eslint-disable-next-line no-undef
const props = defineProps(['question'])
// eslint-disable-next-line no-undef
const emit = defineEmits(['selectOption'])

const selectOption = (option) => {
    emit('selectOption', option.isCorrect)
}
</script>

<style scoped>
.question {
    margin: 30px 0;
    padding: 20px;
    background-color: #f9f9f9;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    font-family: Arial, sans-serif;
    color: #333;
    transition: background-color 0.3s ease;
}

.question h2 {
    font-size: 24px;
    margin-bottom: 15px;
    color: #2c3e50;
}

.question ul {
    list-style: none;
    padding: 0;
    margin: 0;
}

.question li {
    padding: 10px;
    border: 1px solid #ccc;
    margin-bottom: 8px;
    cursor: pointer;
    transition: background-color 0.2s;
    border-radius: 5px;
}

.question li:hover {
    background-color: #eee;
    border-color: #bbb;
}
</style>
