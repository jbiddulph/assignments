<template>
  <section v-show="assignments.length">
    <h2 class="font-bold mb-2">{{ title }}</h2>
    <ul class="border rounded border-gray-600 divide-y divide-gray-600">
      <AssignmentItem
        v-for="assignment in assignments"
        :key="assignment.id"
        :assignment="assignment"
      />
    </ul>
  </section>
</template>

<script>
import { AssignmentItem } from "@/components/AssignmentItem.vue";
export default {
  components: { AssignmentItem },
  props: {
    assignments: Array,
    title: String,
  },
};
</script>
