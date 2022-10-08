<template>
  <section class="space-y-6">
    <assignment-list
      :assignments="filters.inProgress"
      title="In Progress"
    ></assignment-list>
    <assignment-list
      :assignments="filters.completed"
      title="Completed Assignments"
    ></assignment-list>
    <form @submit.prevent="add">
      <div class="border border-gray-600 text-black">
        <input
          v-model="newAssignment"
          placeholder="New Assignment"
          class="p-2"
        />
        <button type="submit" class="bg-white p-2 border-l">Add</button>
      </div>
    </form>
  </section>
</template>

<script>
import AssignmentList from "@/components/AssignmentList.vue";
export default {
  components: {
    AssignmentList,
  },
  data() {
    return {
      assignments: [
        { id: 1, name: "do homework", complete: false },
        { id: 2, name: "finish book", complete: false },
        { id: 3, name: "learn code", complete: false },
        { id: 4, name: "Walk the dog", complete: false },
      ],
      newAssignment: "",
    };
  },
  computed: {
    filters() {
      return {
        inProgress: this.assignments.filter(
          (assignment) => !assignment.complete
        ),
        completed: this.assignments.filter((assignment) => assignment.complete),
      };
    },
  },
  methods: {
    add() {
      alert("New assignment added!");
      this.assignments.push({
        name: this.newAssignment,
        completed: false,
        id: this.assignments.length + 1,
      });
    },
  },
};
</script>
