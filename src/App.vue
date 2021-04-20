<template>
  <div>
    <UserForm :onAddUser="handleOnAddUser" />

    <div>
      <ul>
        <li v-for="user in users" :key="user.name">
          {{ user.name }} | {{ user.email }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import UserForm from './components/UserForm.vue';

export default {
  components: { UserForm },
  data() {
    return {
      users: [
        {
          name: "Samuel Martins",
          email: "a@a.com",
        },
        {
          name: "Jeff Bezos",
          email: "b@b.com",
        },
      ],
    };
  },
  methods: {
    handleOnAddUser(user) {
      console.log(user);
      this.users = this.users.concat(user);
    },
  },
};
</script>
