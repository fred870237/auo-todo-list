<script setup>
import { ref, defineEmits } from "vue"

const taskName = ref("")
const taskRemark = ref("")

const emits = defineEmits(["add-task"])

const addTask = () => {
  emits("add-task", taskName.value, taskRemark.value)
  taskName.value = ""
  taskRemark.value = ""
}
</script>

<template>

<div class="flex items-center gap-2 mt-2">
    <label class="mt-5">任務名稱 : </label>    
  </div>

<div class="flex items-center gap-2 mt-1">
    <input
      v-model.trim="taskName"
      @keydown.enter="addTask"
      type="text"
      class="w-full input input-bordered"
      placeholder="輸入點待辦事項吧~"
    />
    <button @click="addTask" class="btn btn-primary">新增任務</button>
  </div>

  <div class="flex items-center gap-2 mt-4">
    <label class="mt-5">備註 : </label>    
  </div>

  <div class="flex items-center gap-2 mt-1">
<p>{{ message }}</p>
<br>
<textarea v-model.trim="taskRemark"
rows="6"
style="background-color:#d9dbe9;"
class="w-full input-bordered height-500px"
></textarea>
  </div>

</template>
