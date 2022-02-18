<template>
	<form v-on:submit.prevent="submitForm">
		<div>
			<label for="username">id : </label>
			<input id="username" type="text" v-model="username" />
		</div>
		<div>
			<label for="password">password : </label>
			<input id="password" type="password" v-model="password" />
		</div>
		<button type="submit">login</button>
	</form>
</template>

<script>
import axios from "axios";
export default {
	data: function () {
		return {
			username: "", //null도 상관없지만 나중에 str이 들어올것을 생각하고 빈문자열을 둠
			password: ""
		};
	},
	methods: {
		submitForm: function (event) {
			// event.preventDefault();
			console.log(this.usename, this.password);
			var url = "https://jsonplaceholder.typicode.com/users";
			var data = {
				username: this.username,
				password: this.password
			};
			axios
				.post(url, data)
				.then(function (response) {
					console.log(response);
				})
				.catch(function (error) {
					console.log(error);
				});
		}
	}
};
</script>

<style></style>
