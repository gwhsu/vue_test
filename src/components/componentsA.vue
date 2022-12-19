<template>
    <button v-on:click="changeView(1)">顯示單向綁定</button>
    <button v-on:click="changeView(2)">顯示雙向綁定</button>
    <button v-on:click="changeView(123)">畫面</button>
    <div class= "container-1" v-if="view===1">
        <p>資料綁定 (單向綁定)</p>
        {{ data }}
    </div>

    <div class= "container-2" v-if="view===2">
        <p>資料綁定 (雙向綁定)</p>
        <input type = "text" v-model = "text" />
        <p>{{ text }}</p>
    </div>
    
    <div v-if="view!==1 && view!==2"> 
        沒畫面
    </div>

</template>

<script setup>
import {ref} from "@vue/reactivity"

const data = " Hello Vue "
const text = ref("1233")
const view = ref(1)
const changeView = (index) =>{
    view.value = index
}

</script>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
