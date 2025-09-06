<template>
   <div class = "person">
        <p> {{ name }}</p>
        <p> {{ age }} </p>
        <button @click="changeName">cn</button>
        <button @click="changeAge">ca</button>
   </div>
</template>

<script lang = "ts" setup>
// reactive 不能修改整体
import { reactive } from 'vue';
import {ref, toRefs} from 'vue'

    let person = reactive( {
        name: "zhang",
        age: 18
    })

    let {name, age} = toRefs(person)
    let x = toRefs(person)

    console.log(x)
    function changeName() {
        name.value += "~" //注意加value
    }

    function changeAge() {
        age.value += 1
    }

   
</script>

<style>
    
</style>