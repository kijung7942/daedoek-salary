<template>
  <v-row justify="end" class="pa-4" no-gutters>
    <v-btn icon="mdi-plus" @click="test"></v-btn>
  </v-row>
  <v-card>
    <v-card-title>연봉 차트</v-card-title>
    <v-card-text>
      <!-- 차트 라이브러리를 사용하여 여기에 차트를 구현하세요 -->
    </v-card-text>
  </v-card>
  <v-divider class="pt-3" />
  <v-card>
    <v-card-title>연봉 리스트</v-card-title>
    <v-table fixed-header>
      <thead>
        <tr>
          <th class="text-center">닉네임</th>
          <th class="text-center">나이</th>
          <th class="text-center">경력</th>
          <th class="text-center">지역</th>
          <th class="text-center">회사명</th>
          <th class="text-center">연봉</th>
          <th class="text-center">학벌</th>
          <th class="text-center">전공</th>
          <th class="text-center">경력</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="data in datas" :key="data.nickName">
          <td class="text-center">
            {{ data.anonymous ? '익명' : data.nickName }}
          </td>
          <td class="text-center">{{ data.age }}</td>
          <td class="text-center">{{ data.career }}</td>
          <td class="text-center">{{ data.region }}</td>
          <td class="text-center">{{ data.companyName }}</td>
          <td class="text-center">{{ data.salry.toLocaleString() }}</td>
          <td class="text-center">{{ data.education }}</td>
          <td class="text-center">{{ data.major }}</td>
          <td class="text-center">{{ data.career }}</td>
        </tr>
      </tbody>
    </v-table>
  </v-card>
</template>

<script lang="ts" setup>
import { PropType } from 'vue'

interface SalaryData {
  experience: number
  salary: number
  location: string
}

defineProps({
  data: {
    type: Array as PropType<SalaryData[]>,
    required: true,
  },
})

const datas = [
  {
    nickName: '이름',
    anonymous: true,
    age: '나이',
    region: '지역',
    companyName: '회사명',
    salry: 4000,
    education: '대졸',
    major: '컴퓨터 공학',
    career: '만 4년(5년차)',
  },
]

// 차트 구현 로직을 여기에 추가하세요
</script>
