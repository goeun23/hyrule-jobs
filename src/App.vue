<template>
  <div class="app">
    <header>
      <div class="order">
      <button @click="handleClick('title')"> order by title</button>
      <button @click="handleClick('salary')"> order by salary</button>
      <button @click="handleClick('location')"> order by location</button>
     </div>
    </header>
    <JobList :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import Job from "./types/Job";
import OderTerm from "./types/OderTerm";
import JobList from "./components/JobList.vue";
export default defineComponent({
  name: "App",
  components: {
    JobList,
  },
  setup() {
    // const state = reactive({
    //   name: "Link",
    //   age: 25 as string | number,
    // });
    // return { ...toRefs(state) };
    // const name = ref("Link");
    // const age = ref<number | string>(23);
    // return { name, age };

    const jobs = ref<Job[]>([
      {
        title: "farm worker",
        location: "ranch",
        salary: 23243,
        id: "1",
      },
      {
        title: "farm worker2",
        location: "ranch",
        salary: 34234234,
        id: "2",
      },
      {
        title: "farm worker3",
        location: "ranch",
        salary: 32423423423,
        id: "3",
      },
      {
        title: "farm worker4",
        location: "ranch",
        salary: 303333000,
        id: "4",
      },
      {
        title: "farm worker5",
        location: "ranch",
        salary: 30000,
        id: "5",
      },
    ]);

    const order = ref<OderTerm>('title')

    const handleClick = (term : OderTerm) => {
      order.value = term
    }

    return { jobs, handleClick, order };
  },
});
</script>

<style>
header {
  text-align: center;
}

header .order {
  margin-top: 20px;
}

button {
  margin : 0 10px;
  color : #1195c9;
  border : 3px solid #1195c9;
  padding : 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
</style>
