<script setup lang="ts">
import {ref} from 'vue'

const dialogVisible = ref<boolean>(false)
</script>

<template>
  <el-button @click="dialogVisible = true">open dialog</el-button>
  <el-dialog v-model="dialogVisible" class="custom-class" title="Tips">
    <span>It's a draggable Dialog</span>
    <template #footer>
      <span class="dialog-footer">
        <el-button @click="dialogVisible = false">Cancel</el-button>
        <el-button type="primary" @click="dialogVisible = false">
          Confirm
        </el-button>
      </span>
    </template>
  </el-dialog>
</template>

<style scoped>
.custom-class{
  background-color: #ff6700;
}
</style>
