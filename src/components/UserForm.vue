<template>
  <div>
    <form @submit.prevent="onFormSubmit">
      <p>
        <label>First name:</label>
        <input type="text" v-model="firstName" />
      </p>
      <p>
        <label>Last name:</label>
        <input type="text" v-model="lastName" />
      </p>
      <p>
        <label>E-mail:</label>
        <input type="text" v-model="email" />
      </p>
      <button type="submit">Send</button>
    </form>
    <!-- Atualização das propriedades -->
    <p>{{ firstName }} {{ lastName }} | {{ email }}</p>
  </div>
</template>

<script>
export default {
  name: "UserForm",
  data() {
    return {
      firstName: "",
      lastName: "",
      email: "",
    };
  },
  props: {
    onAddUser: Function,
  },
  methods: {
    onFormSubmit() {
      const user = {
        name: `${this.firstName}  ${this.lastName}`,
        email: this.email,
      };

      this.onAddUser(user);
    },
  },
};
</script>
