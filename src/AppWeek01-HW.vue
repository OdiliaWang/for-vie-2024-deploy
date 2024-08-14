<script setup>
import { ref } from 'vue';

// 1.拿到table資料，先轉為陣列形式
// 2.到template刻畫面
// 2.1 const 定義飲料菜單drinks的ref資料從哪來
// 2.2 v-for 渲染陣列資料->指定的區塊
const drinks = ref([
  {
    id: '1',
    name: '珍珠奶茶',
    description: '香濃奶茶搭配QQ珍珠',
    price: '50',
    stock: '20'
  },{
    id: '2',
    name: '珍珠奶茶',
    description: '清新冬瓜配上新鮮檸檬',
    price: '45',
    stock: '18'
  },{
    id: '3',
    name: '翡翠檸檬',
    description: '綠茶與檸檬的完美結合',
    price: '55',
    stock: '34'
  },{
    id: '4',
    name: '四季春茶',
    description: '香醇四季春茶，回甘無比',
    price: '45',
    stock: '10'
  },{
    id: '5',
    name: '阿薩姆奶茶',
    description: '阿薩姆紅茶搭配香醇鮮奶',
    price: '50',
    stock: '25'
  },{
    id: '6',
    name: '檸檬冰茶',
    description: '檸檬與冰茶的清新組合',
    price: '45',
    stock: '20'
  },{
    id: '7',
    name: '芒果綠茶',
    description: '芒果與綠茶的獨特風味',
    price: '55',
    stock: '18'
  },{
    id: '8',
    name: '抹茶拿鐵',
    description: '抹茶與鮮奶的絕配',
    price: '60',
    stock: '20'
  }
]);



</script>

<template>
  <h1>2024 Vue前端新手營 第一週作業</h1>
  <br>
  <div class="">
    <table>
      <thead>
        <tr>
          <th scope="col">品項</th>
          <th scope="col">描述</th>
          <th scope="col">價格</th>
          <th scope="col">庫存</th>
        </tr>
      </thead>

      <tbody>
        <tr v-for="drink in drinks" :key="drink.id">
          <td> {{ drink.name }} </td>
          <td> {{ drink.description }} </td>
          <td> {{ drink.price }} </td>
          <td><button type="button">-</button> {{ drink.stock }} <button type="button">+</button></td>
          <td><button type="button" @click="confirmEdit">確認編輯</button></td>
          <td><button type="button" @click="tempEdit = {}">取消</button></td>

        </tr>
      </tbody>
    </table>
  </div>
</template>
