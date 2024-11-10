<template>
  <div>
    <header>
      <h1>Quizes</h1>
      <input v-model.trim="search" type="text" placeholder="Search..." />
    </header>

    <div class="options-container">
      <Card v-for="quiz in quizes" :key="quiz.id" :quiz="quiz" />
    </div>
  </div>

  <div>
    <p>Learn about animations and transitions.</p>
    <div class="container">
      <Transition name="fade">
        <h2 v-if="showGreet">Hello World</h2>
        <h2 v-else>Goodbye World</h2>
      </Transition>
      <button @click="showGreet = !showGreet">Toggle Me!</button>
    </div>
  </div>
</template>

<script setup>
import Card from "../components/Card.vue";
import { ref, watch } from "vue";
import q from "../data/quizes.json";

const search = ref("");
const quizes = ref(q);

const showGreet = ref(true);

watch(search, () => {
  quizes.value = q.filter((quiz) =>
    quiz.name.toLowerCase().includes(search.value.toLowerCase())
  );
});
</script>

<style scoped>
.container {
  max-width: 1000px;
  margin: 0 auto;
}

header {
  margin-bottom: 10px;
  margin-top: 30px;
  display: flex;
  align-items: center;
}

header h1 {
  font-weight: bold;
  margin-right: 30px;
}

header input {
  border: none;
  background-color: rgba(128, 128, 128, 0.1);
  padding: 10px;
  border-radius: 5px;
}

.options-container {
  display: flex;
  flex-wrap: wrap;
  margin-top: 40px;
}

.fade-enter-from {
  /* background-color: lightblue; */
  opacity: 0;
}

.fade-enter-to {
  /* background-color: aquamarine; */
  opacity: 1;
}

.fade-enter-active {
  transition: all 1s ease;
}

.fade-leave-from {
  /* background-color: lightblue; */
  opacity: 1;
}

.fade-leave-to {
  /* background-color: aquamarine; */
  opacity: 0;
}

.fade-leave-active {
  transition: all 1s ease;
}

.container {
  position: relative;
}

h2 {
  position: absolute;
}

button {
  margin-top: 50px;
}
</style>
