<template>
  <div>
    <header>
      <h4>Question</h4>
      <div class="bar">
        <div class="completion"></div>
      </div>
    </header>
    <div>
      <div class="question-container">
        <h1 class="question"></h1>
      </div>
      <div class="option-container">
        <div class="option">
          <p class="option-label">A</p>
          <div class="option-value">
            <p></p>
          </div>
        </div>
        <div class="option">
          <p class="option-label">B</p>
          <div class="option-value">
            <p></p>
          </div>
        </div>
        <div class="option">
          <p class="option-label">C</p>
          <div class="option-value">
            <p></p>
          </div>
        </div>
        <div class="option">
          <p class="option-label">D</p>
          <div class="option-value">
            <p></p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
header {
  margin-top: 20px;
}

header h4 {
  font-size: 30px;
}

.bar {
  width: 300px;
  height: 50px;
  border: 3px solid bisque;
}

.completion {
  height: 100%;
  width: 0%;
  background-color: bisque;
}

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
