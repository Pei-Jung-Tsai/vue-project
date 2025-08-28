<script setup>
//import HelloWorld from './components/HelloWorld.vue'
//import TheWelcome from './components/TheWelcome.vue'
//import JSON from './components/JSON.vue'
import Form from './components/Form.vue'
import DataTable from 'primevue/datatable'
import Column from 'primevue/column'
import { ref } from 'vue'

const users = ref([])
const addUser = (user) => {
  users.value.push(user)
}
</script>

<template>
  <header>
    <!--<img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
     <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>-->
  </header>

  <main>
    <!--<TheWelcome />-->
    <!--<JSON />-->
    <!--<Form />-->
    <Form @submit="addUser" />
    <DataTable :value="users" class="mt-4">
      <Column field="username" header="Username" />
      <Column field="password" header="Password" />
      <Column field="isAustralian" header="Australian Resident" />
      <Column field="gender" header="Gender" />
      <Column field="reason" header="Reason" />
    </DataTable>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
