<script setup lang="ts">
import { useI18n } from 'vue-i18n'
const { t, availableLocales, locale } = useI18n()
const toggleLocales = () => {
  // change to some real logic
  const locales = availableLocales
  locale.value = locales[(locales.indexOf(locale.value) + 1) % locales.length]
}

const getANewQuestion = () => {
  alert ("Button Click")
}

</script>

<template>

    
  <div> 
    <button 
      class="icon-btn mx-2 !outline-none" 
      title="Randomize a new question" 
      @click="getANewQuestion"
    >
          New Question
    </button>
  </div>

</template>
