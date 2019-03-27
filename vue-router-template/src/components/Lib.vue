<template>
	<div>
		<div class="top-bar">
			<router-link to="/qusetion_bank">题库</router-link>
			<router-link to="/resource_pool">资源库</router-link>
			<router-link to="/activity_library">活动库</router-link>
		</div>
		<div class="content"><router-view /></div>
	</div>
</template>

<script>
export default {
	name: 'Lib',
	data() {
		return {
			
		};
	}
};
</script>

<style scoped>
.container {
	display: flex;
	width: 90%;
	margin: 0 auto;
	
}
.top-bar {
	flex: 1 1 20%;
	display: flex;
	margin-left: 20px;
	background-color: #fff;
	margin-top: 20px;
	width: 875px;
}
a{
	margin-bottom: 30px;
}
.content{
	flex: 1 1 80%;
	text-align: left;
	background-color: #fff;
	margin-left: 20px;
	padding-bottom: 20px;
}
</style>

