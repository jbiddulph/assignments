<template>
  <div class="home">
    <AssignmentItems />
  </div>
</template>

<script>
import AssignmentItems from "@/components/AssignmentItems.vue";

export default {
  name: "HomeView",
  components: {
    AssignmentItems,
  },
};
</script>
