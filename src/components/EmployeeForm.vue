<<<<<<< Updated upstream
<template>
  <div id="employee-form">
    <form>
      <label>Employee name</label>
      <input v-model="employee.name" type="text" />
      <label>Employee Email</label>
      <input v-model="employee.email" type="text" />

      <button>Add Employee</button>
      <employee-form @add:employee="addEmployee" />
      <form @submit.prevent="handleSubmit"></form>

      <form @submit.prevent="handleSubmit">
        <label>Employee name</label>
        <input
          ref="first"
          type="text"
          :class="{ 'has-error': submitting && invalidName }"
          v-model="employee.name"
          @focus="clearStatus"
          @keypress="clearStatus"
        />
        <input ref="first" ... />

        <label>Employee Email</label>

        <input
          type="text"
          :class="{ 'has-error': submitting && invalidEmail }"
          v-model="employee.email"
          @focus="clearStatus"
        />
        <p v-if="error && submitting" class="error-message">❗Please fill out all required fields</p>
        <p v-if="success" class="success-message">✅ Employee successfully added</p>
        <button>Add Employee</button>
      </form>
    </form>
  </div>
</template>

<script>
export default {
  name: "employee-form",

  data() {
    return {
      submitting: false,
      error: false,
      success: false,
      employee: {
        name: "",
        email: ""
      }
    };
  },

  methods: {
    handleSubmit() {
      this.submitting = true;
      this.clearStatus();

      if (this.invalidName || this.invalidEmail) {
        this.error = true;
        return;
      }

      this.$emit("add:employee", this.employee);
      this.employee = {
        name: "",
        email: ""
      };
      this.error = false;
      this.success = true;
      this.submitting = false;
    },

    invalidName() {
      return this.employee.name === "";
    },

    invalidEmail() {
      return this.employee.email === "";
    }
  }
};

// {
//   handleSubmit() {
//     this.submitting = true
//     this.clearStatus()

//     if (this.invalidName || this.invalidEmail) {
//       this.error = true
//       return
//     }

//     this.$emit('add:employee', this.employee)
//     this.employee = {
//       name: '',
//       email: '',
//     }
//     this.error = false
//     this.success = true
//     this.submitting = false
//   }

//   clearStatus() {
//     this.success = false
//     this.error = false
//   }
// }
// this.$emit('add:employee', this.employee)
// this.$refs.first.focus()
</script>

<style scoped>
form {
  margin-bottom: 2rem;
}
</style>

<style scoped>
form {
  margin-bottom: 2rem;
}

[class*="-message"] {
  font-weight: 500;
}

.error-message {
  color: #d33c40;
}

.success-message {
  color: #32a95d;
}
</style>

=======
<template>
  <div id="employee-form">
    <form>
      <label>Employee name</label>
      <input v-model="employee.name" type="text" />
      <label>Employee Email</label>
      <input v-model="employee.email" type="text" />

      <button>Add Employee</button>
      <employee-form @add:employee="addEmployee" />
      <form @submit.prevent="handleSubmit"></form>

      <form @submit.prevent="handleSubmit">
        <label>Employee name</label>
        <input
          ref="first"
          type="text"
          :class="{ 'has-error': submitting && invalidName }"
          v-model="employee.name"
          @focus="clearStatus"
          @keypress="clearStatus"
        />
        <input ref="first" ... />

        <label>Employee Email</label>

        <input
          type="text"
          :class="{ 'has-error': submitting && invalidEmail }"
          v-model="employee.email"
          @focus="clearStatus"
        />
        <p v-if="error && submitting" class="error-message">❗Please fill out all required fields</p>
        <p v-if="success" class="success-message">✅ Employee successfully added</p>
        <button>Add Employee</button>
      </form>
    </form>
  </div>
</template>

<script>
export default {
  name: "employee-form",

  data() {
    return {
      submitting: false,
      error: false,
      success: false,
      employee: {
        name: "",
        email: ""
      }
    };
  },

  methods: {
      clearStatus() {
    this.success = false
    this.error = false
  },
    handleSubmit() {
      this.submitting = true;
      this.clearStatus();

      if (this.invalidName || this.invalidEmail) {
        this.error = true;
        return;
      }

      this.$emit("add:employee", this.employee);
      this.employee = {
        name: "",
        email: ""
      };
      this.error = false;
      this.success = true;
      this.submitting = false;
    },

    invalidName() {
      return this.employee.name === "";
    },

    invalidEmail() {
      return this.employee.email === "";
    }
  }
};

// {
//   handleSubmit() {
//     this.submitting = true
//     this.clearStatus()

//     if (this.invalidName || this.invalidEmail) {
//       this.error = true
//       return
//     }

//     this.$emit('add:employee', this.employee)
//     this.employee = {
//       name: '',
//       email: '',
//     }
//     this.error = false
//     this.success = true
//     this.submitting = false
//   }

//   clearStatus() {
//     this.success = false
//     this.error = false
//   }
// }
// this.$emit('add:employee', this.employee)
// this.$refs.first.focus()
</script>

<style scoped>
form {
  margin-bottom: 2rem;
}
</style>

<style scoped>
form {
  margin-bottom: 2rem;
}

[class*="-message"] {
  font-weight: 500;
}

.error-message {
  color: #d33c40;
}

.success-message {
  color: #32a95d;
}
</style>

>>>>>>> Stashed changes
