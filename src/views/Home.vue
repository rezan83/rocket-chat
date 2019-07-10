<template>
  <div class="home center-align">
    <img id="logo" 	class="" alt="rocket logo" src="../assets/chatrocket.png">
    <Main msg="Welcome to Rocket Chat"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Main from '@/components/Main.vue'

export default {
  name: 'home',
  components: {
    Main
  }
}
</script>

<style>
	#logo {
		margin-top: 10%;
		margin-left: 10%;
		max-width:10%;
	}
</style>