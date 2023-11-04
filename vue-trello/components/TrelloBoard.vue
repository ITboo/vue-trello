<script lang="ts">
import { ref } from "vue";
import { nanoid } from "nanoid";
import type { Column } from "../types/types";
const columns = ref<Column[]>([
  {
    title: "Backlog",
    id: nanoid(),
    tasks: [
      {
        title: "Create marketing landing page",
        createdAt: new Date(),
        id: nanoid(),
      },
      {
        title: "Develop cool new feature",
        createdAt: new Date(),
        id: nanoid(),
      },
      { title: "Fix page nav bug", createdAt: new Date(), id: nanoid() },
    ],
  },
  { title: "Selected for Dev", id: nanoid(), tasks: [] },
  { title: "In Progress", id: nanoid(), tasks: [] },
  { title: "QA", id: nanoid(), tasks: [] },
  { title: "Complete", id: nanoid(), tasks: [] },
]);
</script>

<template>
  <div class="wrapper">
    <header v-for="column in columns" :key="column.id">
      {{ column.title }}
    </header>
    <TrelloBoardTask v-for="task in column.tasks" :task="task" :key="task" />
    <footer>
        <button>
            + Add a Card
        </button>
    </footer>
  </div>
</template>