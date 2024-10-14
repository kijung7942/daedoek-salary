<template>
  <v-form @submit.prevent="handleSubmit">
    <v-text-field
      v-model.number="experience"
      label="경력 (년)"
      type="number"
      required
    ></v-text-field>
    <v-text-field
      v-model.number="salary"
      label="연봉 (만원)"
      type="number"
      required
    ></v-text-field>
    <v-text-field v-model="location" label="근무지역" required></v-text-field>
    <v-btn type="submit" color="primary">제출</v-btn>
  </v-form>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const experience = ref(0)
const salary = ref(0)
const location = ref('')

const emit = defineEmits<{
  (
    e: 'submit',
    data: { experience: number; salary: number; location: string },
  ): void
}>()

const handleSubmit = () => {
  emit('submit', {
    experience: experience.value,
    salary: salary.value,
    location: location.value,
  })
  experience.value = 0
  salary.value = 0
  location.value = ''
}
</script>
