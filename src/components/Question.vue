<template>
  <div class="question-container">
    <h1 class="question">
      {{ question.text }}
    </h1>
  </div>
  <div class="option-container">
    <div
      v-for="option in question.options"
      :key="option.id"
      class="option"
      @click="emitSelectedOption(option.isCorrect)"
    >
      <p class="option-label">{{ option.label }}</p>
      <div class="option-value">
        <p>{{ option.text }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from "vue";

const emit = defineEmits(["selectOption"]);

// emit the selectOption event. Second parameter to pass in isCorrect.
// when @click is selected this event is fired.
// is the option correct or not (true or false).
const emitSelectedOption = (isCorrect) => {
  emit("selectOption", isCorrect);
};

const { question } = defineProps(["question"]);
</script>

<style scoped>
.question-container {
  margin-top: 20px;
}

.question {
  font-size: 40px;
  margin-bottom: 20px;
}

.option {
  display: flex;
  margin-bottom: 20px;
}

.option-label {
  background-color: bisque;
  width: 50px;
  height: 50px;
  font-size: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.option-value {
  background-color: rgb(244, 239, 239);
  width: 100%;
  font-size: 30px;
  padding: 0 20px;
}
</style>
