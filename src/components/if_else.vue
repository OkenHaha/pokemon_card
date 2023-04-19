<template>
	<Child msg="Oken"/>
	<h3>Email: </h3>
	<input type="text" v-model="email" name="">
	<h3>Password: </h3>
	<input type="password" v-model="password" name=""><br/>
	<button @click="login">login</button>
</template>

<script>
	//ok
	import Child from './child.vue'
	export default{
		components: {
			Child
		},
		name: "PAGEONE",
		data() {
			return {
				email: '',
				password: '',
				state: true,
				stack: ["JS", "Python", "Vue", "MERN", "Django", "FastAPI", "Flask"],
				users: [{email: "test@gmail.com", password: "pass123"},{email:"new@mail.com", password: "test123"}]
			};
		},
		methods:{
			login(){
				// if(this.email == this.users[email] && this.password == this.users[password]) {
				// 	alert("Login correct")
				// }
				// else{
				// 	alert("incorrect login. Please check email or password entered")
				// }
				//console.log(this.users[0].email)
				for(let x in this.users) {
					if(this.email == this.users[x].email && this.password == this.users[x].password) {
						alert("ok")
					}
				}
			}
		}
	}
</script>