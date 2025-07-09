<template>
  <div class="signup-container">
    <h2>Create an Account</h2>
    <form @submit.prevent="handleSubmit">
      <div class="form-group">
        <label for="name">Full Name</label>
        <input id="name" v-model="form.name" type="text" name="name" placeholder="John Doe" required />
      </div>
      <div class="form-group">
        <label for="email">Email Address</label>
        <input id="email" v-model="form.email" type="email" name="email" placeholder="you@example.com" required />
      </div>
      <div class="form-group">
        <label for="password">Password</label>
        <input id="password" v-model="form.password" type="password" name="password" placeholder="********" required />
      </div>
      <div class="form-group">
        <label for="confirm_password">Confirm Password</label>
        <input id="confirm_password" v-model="form.confirmPassword" type="password" name="confirm_password" placeholder="********" required />
      </div>
      <button type="submit">Sign Up</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'SignupForm',
  data() {
    return {
      form: {
        name: '',
        email: '',
        password: '',
        confirmPassword: ''
      }
    }
  },
  methods: {
    handleSubmit() {
      if (this.form.password !== this.form.confirmPassword) {
        alert("Passwords do not match!");
        return;
      }

      alert(`Signed up as ${this.form.name}`);
    }
  }
}
</script>

<style scoped>
.signup-container {
  background-color: #ffffff;
  padding: 2rem;
  margin: 2rem auto;
  max-width: 400px;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  font-family: 'Segoe UI', sans-serif;
  align-items: center;
}

h2 {
  text-align: center;
  margin-bottom: 1.5rem;
  color: #333;
}

.form-group {
  margin-bottom: 1rem;
 
}

label {
  display: block;
  margin-bottom: 0.25rem;
  font-weight: 600;
  color: #444;
}

input {
  width: 100%;
  padding: 0.75rem;
  border: 1px solid #ccc;
  border-radius: 6px;
  font-size: 1rem;
  box-sizing: border-box;
}

button {
  width: 100%;
  padding: 0.75rem;
  background-color: #28a745;
  color: white;
  font-size: 1rem;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

button:hover {
  background-color: #218838;
}

@media (max-width: 480px) {
  .signup-container {
    padding: 1.5rem;
    width: 90%;
  }
}
</style>

