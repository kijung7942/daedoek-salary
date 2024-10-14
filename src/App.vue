<template>
  <v-layout class="h-full">
    <v-app-bar rounded :elevation="6" title="DDIT SALARY"> </v-app-bar>

    <v-navigation-drawer>
      <v-list class="pt-0" :items="menus"></v-list>
    </v-navigation-drawer>
    <v-main class="d-flex align-start justify-center" style="min-height: 100vh">
      <RouterView />
    </v-main>
  </v-layout>
</template>

<script setup lang="ts">
import { RouterView } from 'vue-router'

const menus = [
  { title: '연봉리스트', value: 1, props: { prependIcon: 'mdi-currency-usd' } },
  { title: '자유게시판', value: 2, props: { prependIcon: 'mdi-post' } },
  {
    title: '대덕블라인드',
    value: 3,
    props: { prependIcon: 'mdi-roller-shade' },
  },
]
</script>

<style scoped></style>
