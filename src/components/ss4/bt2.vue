<template>
<div>
    <div>company: {{company.name}}</div>
    <div>age: {{company.age}}</div>
    <button @click="changeData">change data</button>
</div>

  
</template>

<script setup> 
import {ref} from "vue"
const company = ref({
    name: "rikkei academy",
    age: 1
})

const changeData = () => {
    company.value.name = "rikkei education"
    company.value.age = 3
}




</script>

<style>

</style>