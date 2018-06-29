<template>
	<div class="task">
		<slot>默认内容</slot>
	</div>
</template>

<script type="text/javascript">
	export default {
		name: "task"
	}
</script>

<style scoped>
	.task{
		color: #fff;
	}
</style>