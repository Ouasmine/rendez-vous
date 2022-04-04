<template>
  <div id="app">
    <div class="navbar navbar-dark bg-dark">
      <a href="#" class="navbar-brand">DABADOC</a>
      <ul class="nav">
        <li class="nav-item px-3">
          <router-link class="text-white" to="/login">Login</router-link>
        </li>
        <!-- <li class="nav-item px-3">
          <router-link class="text-white" to="#">mon compte</router-link>
        </li> -->
        <li class="nav-item px-3">
          <router-link class="text-white" to="/signup">Signup</router-link>
        </li>
        <li class="nav-item px-3">
          <a href="#" @click.prevent="Logout" style="color: white">Logout</a>
        </li>
      </ul>
    </div>
  </div>
</template>