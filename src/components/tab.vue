<template>
	
		<div class="tab-inner" v-show="isActive">
			<slot></slot>
		</div>
</template>

<script type="text/javascript">
	export default {
		name: 'tab',
		props: {
			name:{require:true},
        	selected: {default:false}
		},
		data () {
			return {
				isActive : false
			}
		},
		computed:{
	        href(){
	            return '#' + this.name.toLowerCase().replace(/ /g,'-');
	        }
	    },
		mounted () {
			this.isActive = this.selected;
		}
	}
</script>

<style scoped>
.tab-inner{
	color: #fa8d3e;
	font-size: 14px;
	padding: 1.5rem 1rem;
}	
</style>