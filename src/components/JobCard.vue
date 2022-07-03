<template>
  <div>
      <p>Ordered by {{ order }}</p>
    <ul v-for="job in jobs" :key="job.id">
      <div class="bg-red-400">
        <h1>{{ job.title }}</h1>
        <small> salary: {{ job.salary }} </small>
        <p>Location: {{ job.location }}</p>
      </div>
    </ul>
  </div>
</template>
<script setup lang="ts">
import type OrderTerm from "@/types/orderTerm";
import type { PropType } from "@vue/runtime-core";
import type Job from "../types/job";
const props = defineProps({
  jobs: {
    type: Array as PropType<Job[]>,
  },
  order:{
      type: String as PropType<OrderTerm>,
      required:true
  }
})

</script>