<script setup>
import { ref } from 'vue'

const text = ref('這是一段文字')
const city = ref('台北市')
const isChecked = ref('true')
const arrayCheckbox = ref([])
const radioValue = ref('男')
</script>

<template>
  <div>
    <h1>{{ text }}</h1>
    <input type="text" v-model="text" />
    <!-- 表單 -->
    {{ city }}
    <select name="" id="" v-model="city">
      <option value="台北市">台北市</option>
      <option value="台中市">台中市</option>
      <option value="高雄市">高雄市</option>
      <option value="宜蘭市">宜蘭市</option>
    </select>

    <!-- checkbox 1. true falde, 2. value-->
    <hr />
    {{ isChecked }}
    <input type="checkbox" v-model="isChecked" />
    <hr />
    {{ arrayCheckbox }}
    <input type="checkbox" v-model="arrayCheckbox" value="芹菜" />
    <input type="checkbox" v-model="arrayCheckbox" value="小黃瓜" />
    <input type="checkbox" v-model="arrayCheckbox" value="番茄" />
    <hr>
    <!-- radio -->
    {{ radioValue }}
    <input type="radio" v-model="radioValue" value="男" />
    <input type="radio" v-model="radioValue" value="女" />
  </div>
</template>
