<script setup>
// eslint-disable-next-line no-undef
const props = defineProps([
    "questionStatus",
    "barPercentage"
])
</script>

<template>
    <header>
        <h4>Question {{ props.questionStatus }}</h4>
        <div class="bar">
            <div class="completion" :style="{ width: props.barPercentage }"></div>
        </div>
    </header>
</template>

<script>
export default {
    name: 'QuizHeader'
}
</script>

<style scoped>
header {
    margin-top: 20px;

}

header h4 {
    font-size: 30px;

}

.bar {
    width: 100%;
    height: 50px;
    border: 3px solid bisque;
    border-radius: 10px;
    background-color: #f0f0f0;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    position: relative;
    transition: background-color 0.3s ease;
}

.completion {
    height: 100%;
    width: 0%;
    background-color: bisque;
    border-radius: 10px;
    transition: width 0.3s ease;
    position: absolute;
    top: 0;
}
</style>
