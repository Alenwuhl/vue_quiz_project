<script setup>
// eslint-disable-next-line no-undef
const props = defineProps(['quizQuestionLength', 'numberOfCorrectAnswers'])
</script>

<template>
  <div class="results">
    <template v-if="props.numberOfCorrectAnswers === 0">
      <p>Ouch! You didn't get any questions right 😢</p>
      <p>Don't worry, learning takes time</p>
      <p>I recommend you to try again!</p>
      <br>
      <RouterLink to="/" class="button">Go Back</RouterLink>
    </template>

    <template v-else>
      <p>Congratulations! You have completed the quiz.</p>
      <p>You answered correctly:</p>
      <h1>
        {{ props.numberOfCorrectAnswers }}/{{ props.quizQuestionLength }} questions.
      </h1>
      <p>Thank you for participating!</p>
      <p>Click the button below to go back to the home page.</p>
      <br>
      <RouterLink to="/" class="button">Go Back</RouterLink>
    </template>
  </div>
</template>


<style scoped>
.results {
    text-align: center;
    padding: 100px 0;
    background-color: #f0f0f0;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    margin: 20px;
    font-family: Arial, sans-serif;
    color: #333;
    transition: background-color 0.3s ease;
}

p {
    font-size: 25px;
}

h1 {
    font-size: 80px;
}

.button {
    display: inline-block;
    padding: 15px 30px;
    background-color: #3498db;
    color: white;
    text-decoration: none;
    border-radius: 5px;
    font-size: 20px;
    transition: background-color 0.3s ease, transform 0.2s ease;
}
</style>
