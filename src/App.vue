<template>
  <div id="app">

  <nav class="indigo lighten-3">
    <div class="nav-wrapper">
      <a href="#" class="brand-logo">Rocket Chat</a>
      <ul id="nav-mobile" class="right hide-on-down">
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/chat">Chat</router-link></li>
      </ul>
    </div>
  </nav>

    <router-view/>


  </div>
</template>

<style>

</style>
