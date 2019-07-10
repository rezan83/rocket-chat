<template>
  <div class="main">
    <h1>{{ msg }}</h1>

     <div class="row ">
      <form @submit.prevent='goChat' class="col s12">
        <div class="row">
          <div class="input-field col s6">
            <i class="material-icons prefix">account_circle</i>
            <input id="name"  v-model="name" type="text" class="validate">
            <label for="name">Your Name</label>
            <p v-show="inputErr" class="red-text">enter a name please</p>
            <button class="pulse btn-floating right">Go</button>
          </div>

        </div>
      </form>
    </div>
  
  </div>
</template>

<script>
export default {
  name: 'Main',
  props: {
    msg: String
  },
  data(){
    return{
      name: '',
      inputErr: false
    }
  },
  methods: {
    goChat(){
      if (this.name) {
        this.$router.push({ name: 'chat', params: { name: this.name } })
        this.inputErr = false
        this.name = ''
      }else{
        this.inputErr = true
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
