<template>
	<div class="container">
	  <header class="header">
	    <slot name="header"></slot>
	  </header>
	  <main class="main">
	    <slot></slot>
	  </main>
	  <footer class="footer">
	    <slot name="footer"></slot>
	  </footer>
	</div>
</template>

<script type="text/javascript">
	export default {
		name: 'slotComp'
	}
</script>
<style scoped>
	.header h1{
		font-size: 24px;
		color: #fff;		
	}
	.main p{
		font-size: 16px;
		color: #fff;
	}
	.footer p{
		font-size: 12px;
		color: #fff;
	}
</style>