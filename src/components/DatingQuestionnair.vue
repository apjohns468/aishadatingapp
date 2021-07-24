<script setup lang="ts">
import {ref} from 'vue'
import { useI18n } from 'vue-i18n'
const { t, availableLocales, locale } = useI18n()
const toggleLocales = () => {
  // change to some real logic
  const locales = availableLocales
  locale.value = locales[(locales.indexOf(locale.value) + 1) % locales.length]
}

let questionIndex = null

const questions = [
  //0
  'What’s your favorite international food?',
  'Are you a morning person or a night owl?',
  'What’s your favorite restaurant?',
  'How many siblings do you have?',
  'What would be your dream job?',
  'What would you do if had enough money to not need a job?',
  'Who is your favorite author?',
  'What was the last show you binge-watched?',
  'What TV series do you keep coming back to and re-watching'
]

const getANewQuestion = () => {
  const randomNumber = Math.floor(Math.random() * questions.length)
  
  questionIndex = randomNumber
  //'return questions[randomNumber]
}

</script>

<template>

    
  <div> 
    {{ questions[questionIndex] }}
    <button 
      class="QuestionButton"
      title="Randomize a new question" 
      @click="getANewQuestion"
    >
          New Question
    </button>
  </div>


</template>
