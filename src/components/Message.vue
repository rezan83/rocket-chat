
<template>
	 <div class="message">
	 	<form @submit.prevent="addMessage">
	 		<label for="addmessage">type your message</label>
    		<input name="addmessage" type="text" v-model='message'>
    		<div class="red-text" v-if="emptyMessage">{{emptyMessage}}</div>
	 	</form>
    </div>
</template>

<script>
export default {

  name: 'Message',
  props: ['name'],
  data () {
    return {
    	message: '',
    	emptyMessage: ''
    }
  },
  methods: {
  	addMessage(){
  		if (this.message) {
  			db.collection('messages').add({
  				content: this.message,
  				name: this.name,
  				time: Date.now()
  			}).catch(err => {
  				console.log(err)
  			})
  			this.message = ''
  			this.emptyMessage = ''
  		}else{
  			this.emptyMessage = 'write a message first please'
  		}
  	}
  }
}
</script>

<style>

</style>