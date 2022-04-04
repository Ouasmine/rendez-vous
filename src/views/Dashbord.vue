<template>
  <div id="app">
    <div class="navbar navbar-dark bg-dark">
      <a href="#" class="navbar-brand">DABADOC</a>
      <ul class="nav">
        <li class="nav-item px-3">
          <router-link class="text-white" to="/login">Home</router-link>
        </li>
        <!-- <li class="nav-item px-3">
          <router-link class="text-white" to="#">mon compte</router-link>
        </li> -->
        <li class="nav-item px-3">
          <router-link class="text-white" to="/Dashbord">Dashboard</router-link>
        </li>
        <li class="nav-item px-3">
          <a href="#" @click.prevent="Logout" style="color: white">Logout</a>
        </li>
      </ul>
    </div>
  </div>
  <!-- <div class="container py-4">
    <div class="home">
      <img alt="Vue logo" src="../assets/logo.png" />
      <HelloWorld msg="Welcome to Your Vue.js App" />
    </div>
  </div> -->
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";

// export default {
//   name: "Home",
//   components: {
//     HelloWorld,
//   },
// };
</script>
