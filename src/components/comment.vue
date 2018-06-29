<template>
	<textarea :value="value" @input="filterComment($event.target.value)">
		
	</textarea>
</template>

<script type="text/javascript">
	export default {
		name: 'comment',
		props:['value'],
		data(){
                return {
                    sensitiveList:['包子','蛤蛤'],
                    replaceWord:'河蟹'
                }
        },
		methods: {
			filterComment (comment) {
				var that = this;
                this.sensitiveList.forEach(function(word){
                    var regex = new RegExp(word,'g');;
                    comment = (comment.indexOf(word) >= 0 ? comment.replace(regex,that.replaceWord) : comment);
                })
				this.$emit('input',comment);
			}
		}
	}
</script>