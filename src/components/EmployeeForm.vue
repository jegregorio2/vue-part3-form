<template>
  <div id="employee-form">
    <!-- add form -->
    <form @submit.prevent="handleSubmit">
      <div class="mb-3">
        <!-- add label -->
        <label for="exampleInputName1" class="form-label">Employee name</label>
        <!-- add input -->
        <input 
          v-model="employee.name"
          type="text"
          class="form-control"
          id="exampleInputName1"
          aria-describedby="nameHelp"
        />
      </div>
      <div class="mb-3">
        <!-- add label -->
        <label for="exampleInputEmail1" class="form-label">Employee email</label>
        <!-- add input -->
        <input 
          v-model="employee.email"
          type="email"
          class="form-control"
          id="exampleInputEmail1"
          aria-describedby="emailHelp"
        />
      </div>
      <!-- add button -->
      <button
        class="btn btn-primary"
        type="submit">Add Employee
      </button>
    </form>
  </div>
</template>

<script>
  export default {
    name: 'EmployeeForm',
    // add data()
    data() {
      return {
        employee: {
          name: '',
          email: '',
        },
      }
    },
    // add methods
    methods: {
      // add handleSubmit()
      handleSubmit() {
        console.log('testing handleSubmit')
        // when you click 'Add Employee' button, you will see 'testing handleSubmit' in console
        this.$emit('add:employee', this.employee)
        // when you click 'Add Employee' button, you will see 'add:employee' through vue > events
      },
    },
  }
</script>

<style scoped>
  form {
    margin-bottom: 2rem;
  }
</style>