<script setup lang="ts">
import { reactive, ref } from "@vue/reactivity";
import type Job from "../types/job";
import type OrderTerm from "../types/orderTerm";
import JobCard from "../components/JobCard.vue";
const jobs = ref<Job[]>([
  {
    title: "Chef",
    location: "lagos",
    salary: 2000,
    id: "1",
  },
  {
    title: "Coder",
    location: "Port harcourt",
    salary: 2000,
    id: "1",
  },
  {
    title: "Cleaner",
    location: "lagos",
    salary: 2000,
    id: "1",
  },
  {
    title: "Teacher",
    location: "lagos",
    salary: 2000,
    id: "1",
  },
  {
    title: "Farmer",
    location: "lagos",
    salary: 2000,
    id: "1",
  },
  {
    title: "Baby-sitter",
    location: "lagos",
    salary: 2000,
    id: "1",
  },
]);

const order = ref<OrderTerm>("title");
const handleClick = (term: OrderTerm) => {
  order.value = term;
  console.log(term);
};
console.log(order.value);
</script>

<template>
  <main>
    <button @click="handleClick('salary')">order by salary</button>
    <button @click="handleClick('location')">order by location</button>
    <button @click="handleClick('title')">order by title</button>
    <JobCard :jobs="jobs" :order="order" />
  </main>
</template>
