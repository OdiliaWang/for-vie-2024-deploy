<script setup>
import { ref } from 'vue'

const text = ref('這是一段文字')

const todos = ref([
  {
    id: 1,
    text: '澆花'
  }
])

const tempEdit = ref({
  id: '',
  text: ''
})

const addTodo = () => {
  todos.value.push({
    text: text.value,
    id: new Date().getTime()
  })
  console.log(todos.value)
  text.value = ''
}

const deleteTodo = (todo) => {
  console.log(todo)
  const index = todos.value.findIndex((items) => items.id === todo.id)
  // JS陣列方法
  console.log(index)
  todos.value.splice(index, 1)
}

const prepareEdit = (todo) => {
  tempEdit.value = { ...todo } // 拷貝
  console.log(tempEdit.value)
  // JS的概念，物件傳參考
}

const confirmEdit = () => {
  const index = todos.value.findIndex((items) => items.id === tempEdit.value.id)
  console.log(index, todos.value)
  // 把 tempEdit 的值，帶回去 todos
  todos.value[index] = tempEdit.value

  tempEdit.value = ''
}
</script>

<template>
  <input type="text" v-model="text" />
  <button type="button" @click="addTodo">新增</button>
  <hr />
  <div v-for="todo in todos" :key="todo.id">
    {{ todo.text }}
    <button type="button" @click="deleteTodo(todo)">刪除</button>
    <button type="button" @click="prepareEdit(todo)">編輯</button>
    <!-- {{ todo.imageUrl }}
    <img :src="todo.imageUrl" alt="" /> -->
    <hr />
  </div>
  <hr />
  <div v-if="tempEdit.id">
    <!-- 判斷是否此區塊要顯示 -->
    <h2>編輯區域</h2>
    當前修改的值：{{ tempEdit.text }}
    <br />
    <input type="text" v-model="tempEdit.text" />
    <button type="button" @click="confirmEdit">確認編輯</button>
    <button type="button" @click="tempEdit = {}">取消</button>
  </div>
</template>
