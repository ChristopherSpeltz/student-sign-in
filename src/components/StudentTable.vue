<template>
  <div>
    <!-- Template/HTML here -->
    <div class="card student-list m-2 p-2">
      <h4 class="card-title">Student List</h4>
      <div id="student-table">
        <table class="table">
          <tr>
            <th>Name</th>
            <th>StarID</th>
            <th>Present?</th>
          </tr>

          <!-- create table 
                   Each row will have a checkbox, bound to the app's data 
                   When the checkbox is checked/unchecked, the student will be signed in/out -->

          <student-row
            v-for="student in students"
            v-bind:student="student"
            v-bind:key="student.starID"
            v-on:student-arrived-or-left="arrivedOrLeft"
          >
          </student-row>
        </table>
      </div>
    </div>
  </div>
</template>

<script>

import StudentRow from '@/components/StudentRow.vue'
export default {
  // create component here
  name: "StudentTable",
  components: {StudentRow},
  emits: ["student-arrived-or-left"],
  props: {
    students: Array,
  },
  methods: {
    arrivedOrLeft(student, present) {
      // emit message to parent
      this.$emit("student-arrived-or-left", student, present);
    },
  },
};
</script>

<style></style>
