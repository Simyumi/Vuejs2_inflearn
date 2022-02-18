<template>
	<header>
		<h1>{{ propsdata }}</h1>
		<div>
			<button v-on:click="sendEvent">send</button>
		</div>
	</header>
</template>

<script>
export default {
	props: ["propsdata"],
	methods: {
		sendEvent: function () {
			this.$emit("renew");
		}
	}
};
</script>

<style>
header {
	width: 100%;
	display: flex;
	text-align: center;
	flex-direction: column;
}
header > h1 {
	color: rgb(63, 49, 190);
}
button {
	width: 5rem;
	height: 3rem;
	text-align: center;
	color: #fff;
	background-color: cornflowerblue;
	border: none;
	border-radius: 8px;
}
button:hover {
	background-color: rgb(200, 230, 255);
	color: rgb(121, 121, 121);
}
</style>
