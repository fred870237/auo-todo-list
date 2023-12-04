<script setup>
import { getTask } from "@/auo-lib/storage"
import { useRoute } from "vue-router"
import { onBeforeMount, reactive } from "vue"

let task = reactive({})

const route = useRoute()
onBeforeMount(() => {
  const { params } = route
  task = getTask(params.auo)
})
</script>

<template>

<div class="divider"></div>

<h1 class="text-4xl">任務 {{ task.title }} 備註 : </h1>
  <div class="mt-5">
    <h1 class="text-2xl">{{ task.remark }}</h1>
  </div>
  
</template>
