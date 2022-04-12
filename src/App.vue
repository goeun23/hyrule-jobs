<template>
  <div class="app">
    <p>{{ jobs[0].location  }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from "vue";
import Job from "./types/Job";
export default defineComponent({
  name: "App",
  components: {},
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
        salary: 30000,
        id: "1",
      },
      {
        title: "farm worker2",
        location: "ranch",
        salary: 30000,
        id: "2",
      },
      {
        title: "farm worker3",
        location: "ranch",
        salary: 30000,
        id: "3",
      },
      {
        title: "farm worker4",
        location: "ranch",
        salary: 30000,
        id: "4",
      },
      {
        title: "farm worker5",
        location: "ranch",
        salary: 30000,
        id: "5",
      },
    ]);

    return { jobs };
  },
});
</script>

<style>
</style>
