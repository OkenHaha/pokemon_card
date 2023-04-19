<template>
	<h1>Hello {{msg}}</h1>
</template>

<script>
	export default{
		name: "child",
		props:{
			msg: String,
		},
	}
</script>