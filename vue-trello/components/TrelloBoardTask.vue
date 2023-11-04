<script lang="ts">
import type { Task } from '../types/types';
const props = defineProps<{
  task: Task;
}>();
</script>

<template>
    <div class="" :title="task.createdAt.toLocaleDateString()">
        <span>{{ task.title }}</span>
    </div>
</template>