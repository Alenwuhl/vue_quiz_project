<!-- QuizCard.vue -->

<script setup>
// eslint-disable-next-line no-undef
const props = defineProps(['quiz'])

import { useRouter } from "vue-router"

const router = useRouter()

const navigateToQuiz = () => {
  router.push(`/quiz/${props.quiz.id}`)
}
</script>

<template>
  <div class="card" @click="navigateToQuiz">
    <img :src="props.quiz.img" alt="Quiz Image" />
    <div class="card-text">
      <h2>{{ props.quiz.name }}</h2>
      <p>{{ props.quiz.questions.length }} questions</p>
    </div>
  </div>
</template>

<style scoped>
.card {
  width: 310px;
  overflow: hidden;
  border-radius: 2%;
  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.1);
  margin-bottom: 35px;
  margin-right: 20px;
  cursor: pointer;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  display: inline-block;
}

.card img {
  width: 100%;
  height: 190px;
  margin: 0;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.card .card-text {
  padding: 0 5px;
  background-color: #f9f9f9;
  text-align: center;
  font-family: Arial, sans-serif;
  color: #333;
  transition: background-color 0.3s ease;
}

.card .card-text h2 {
  font-weight: bold;
  font-size: 20px;
}
</style>
