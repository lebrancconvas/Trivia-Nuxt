<template>
  <div>
    <header>
      <div>
        <h1>Trivia Nuxt</h1>
      </div>
    </header>
    <section id="option-section">
      <div v-for="question in questions" :key="question.id">
        <div id="question">
          <h2>{{ question.id }}) {{ question.question }}</h2>
        </div>
        <div id="choice">
          <v-radio-group v-model="radioGroup">
            <v-radio v-for="choice in question.choices" :key="choice.choice" :label="choice.choice" :value:="choice.choice">
            </v-radio>
          </v-radio-group>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        radioGroup: 1,
        questions: [
          {
            "id": 1,
            "question": "What is the first video of Uncle Roger?",
            "choices": [
              {
                "choice": "Jamie Oliver's Egg Fried Rice",
                "isCorrect": false
              },
              {
                "choice": "Hersha's Egg Fried Rice",
                "isCorrect": true
              },
              {
                "choice": "Jamie Oliver's Thai Green Curry",
                "isCorrect": false
              },
              {
                "choice": "Gordom Ramsay's Egg Fried Rice",
                "isCorrect": false
              }
            ],
            "description": "A is correct because of A."
          }
        ]
      }
    }
  }
</script>

<style scoped>
  header {
    text-align: center;
  }
</style>
