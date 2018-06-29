<template>
	<div>
		<div class="tabs">
			<ul class="tab-list">
				<li class='tab-item'
					v-for="(tab,index) in tabs" 
					:class="{'is-active':tab.isActive===true}"
					:key="index"
					@click="tabSelectedClick(tab)"
				>
					<a class="tab-item-link" 
						:href="tab.href">{{tab.name}}</a>
				</li>
			</ul>
		</div>
		<div class="tab-contents">
			<slot></slot>
		</div>	
	</div>
</template>

<script type="text/javascript">
	export default {
		name: 'zentabs',		
		data() {
			return {
				tabs: []
			}
		},
		mounted () {
			this.tabs = this.$children//$children 获取子组件的数据
		},
		methods: {
			tabSelectedClick (selectedTab) {
				this.tabs.forEach((tab)=>{
					tab.isActive=selectedTab.name===tab.name
				})
			}
		}
	}
</script>

<style scoped>
.tabs{
	height: 45px;
	line-height: 45px;
}
.tab-list{
	display: flex;
}
.tab-item {
	flex: 1;
	border-bottom: 1px solid #999;	
	text-align: center;
}
.tab-item-link{color: #fff;font-size: 16px;}
.tab-item.is-active{
	border-bottom-color:  #fa8d3e;
}
.tab-item.is-active .tab-item-link{color: #fa8d3e;}

</style>