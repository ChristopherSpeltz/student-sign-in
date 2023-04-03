<template>
    <div>
        <!-- Template/HTML here -->
        <!-- show a message when student arrives or leaves  -->

      <div v-if="student.name">
        <div class="alert alert-primary" v-if="student.present">
          Welcome, {{ student.name }}
        </div>

        <div class="alert alert-warning" v-else>
          Goodbye, {{ student.name }}. See you later alligator!
        </div>
      </div>

    </div>
</template>

<script>
export default {
    // create component here
    name: 'StudentMessage',
    props: {
        student: Object
    }

}
</script>

<style scoped>

</style>