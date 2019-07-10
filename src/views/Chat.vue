<template>
  <div class="chat container">
    <h3>hello <span class="blue lighten-4">{{name}}</span> ...just chat!</h3>
    <div class="card" v-chat-scroll>
    	<div class="card-content" >
    		<ul class="messages" >
    			<li  v-for="message in messages" :key="message.time" >
    					
    				<div :class="[message.name === name? 'blue lighten-4' : null, 'chip']">
    				{{message.name}}</div>
    				<div :class="[message.name === name? 'purple lighten-4' : 'red lighten-4', 'chip']">
    				{{message.content}}</div>
    				
    			</li>
    		</ul>
    	</div>
    </div>
   <Message :name="name"/>
  </div>
</template>

<script>
import Message from '@/components/Message'

export default {
  name: 'chat',
  props:['name'],
  components: {
    Message
  },
  data(){
  	return{
  		messages: []
  	}
  },
  created(){
  	db.collection('messages').orderBy('time').onSnapshot(snap => {
  		snap.docChanges().forEach(change =>{
  			if(change.type === 'added'){
  				this.messages.push(change.doc.data())
  			}
  		})
  	})
  }
}
</script>

<style>
.card{
	max-height: 300px;
	overflow: auto;
}
</style>