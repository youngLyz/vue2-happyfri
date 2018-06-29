<template>
    <transition  
    name="custom-classes-transition"
    enter-active-class="animated slideInRight"
    leave-active-class="animated slideOutRight">
    	<article class="message is-black" v-show="isVisiable">
    	  <div class="message-header">
    	    <p class="title">
                <slot name="title">标题</slot>
            </p>
    	    <button @click="hideMessage" class="delete" aria-label="delete"></button>
    	  </div>
    	  <div class="message-body">
    	   <slot name="content"></slot>
    	  </div>
    	</article>
    </transition>    
</template>

<script type="text/javascript">
	export default {
		name: 'message',
        props: {
            isVisiable: Boolean
        },		
		methods: {
			hideMessage () {
				this.$emit('changeShow',false)
			}
		}
	}
</script>

<style scoped>

html{
	font-size: 16px;
}

.delete,.modal-close {
    -moz-appearance: none;
    -webkit-appearance: none;
    background-color: rgba(10,10,10,.2);
    border: none;
    border-radius: 290486px;
    cursor: pointer;
    pointer-events: auto;
    display: inline-block;
    flex-grow: 0;
    flex-shrink: 0;
    font-size: 0;
    height: 20px;
    max-height: 20px;
    max-width: 20px;
    min-height: 20px;
    min-width: 20px;
    outline: 0;
    position: relative;
    vertical-align: top;
    width: 20px
}

.delete::after,.delete::before,.modal-close::after,.modal-close::before {
    background-color: #fff;
    content: "";
    display: block;
    left: 50%;
    position: absolute;
    top: 50%;
    -webkit-transform: translateX(-50%) translateY(-50%) rotate(45deg);
    transform: translateX(-50%) translateY(-50%) rotate(45deg);
    -webkit-transform-origin: center center;
    transform-origin: center center
}

.delete::before,.modal-close::before {
    height: 2px;
    width: 50%
}

.delete::after,.modal-close::after {
    height: 50%;
    width: 2px
}

.delete:focus,.delete:hover,.modal-close:focus,.modal-close:hover {
    background-color: rgba(10,10,10,.3)
}

.delete:active,.modal-close:active {
    background-color: rgba(10,10,10,.4)
}
.message{
    bottom: 0;
    left: 0;
    position: absolute;
    right: 0;
    top: 0;
}
.message {
    background-color: #f5f5f5;
    border-radius: 4px;
    font-size: 16px
}

.message strong {
    color: currentColor
}

.message a:not(.button):not(.tag) {
    color: currentColor;
    text-decoration: underline
}
.title{color: #fff;}
.message.is-small {
    font-size: 12px
}

.message.is-medium {
    font-size: 14px
}

.message.is-large {
    font-size: 24px
}

.message.is-white {
    background-color: #fff
}

.message.is-white .message-header {
    background-color: #fff;
    color: #0a0a0a
}

.message.is-white .message-body {
    border-color: #fff;
    color: #4d4d4d
}

.message.is-black {
    background-color: #fafafa
}

.message.is-black .message-header {
    background-color: #0a0a0a;
    color: #fff
}

.message.is-black .message-body {
    border-color: #0a0a0a;
    color: #090909
}

.message.is-light {
    background-color: #fafafa
}

.message.is-light .message-header {
    background-color: #f5f5f5;
    color: #363636
}

.message.is-light .message-body {
    border-color: #f5f5f5;
    color: #505050
}

.message.is-dark {
    background-color: #fafafa
}

.message.is-dark .message-header {
    background-color: #363636;
    color: #f5f5f5
}

.message.is-dark .message-body {
    border-color: #363636;
    color: #2a2a2a
}

.message.is-primary {
    background-color: #f5fffd
}

.message.is-primary .message-header {
    background-color: #00d1b2;
    color: #fff
}

.message.is-primary .message-body {
    border-color: #00d1b2;
    color: #021310
}

.message.is-link {
    background-color: #f6f9fe
}

.message.is-link .message-header {
    background-color: #3273dc;
    color: #fff
}

.message.is-link .message-body {
    border-color: #3273dc;
    color: #22509a
}

.message.is-info {
    background-color: #f6fbfe
}

.message.is-info .message-header {
    background-color: #209cee;
    color: #fff
}

.message.is-info .message-body {
    border-color: #209cee;
    color: #12537e
}

.message.is-success {
    background-color: #f6fef9
}

.message.is-success .message-header {
    background-color: #23d160;
    color: #fff
}

.message.is-success .message-body {
    border-color: #23d160;
    color: #0e301a
}

.message.is-warning {
    background-color: #fffdf5
}

.message.is-warning .message-header {
    background-color: #ffdd57;
    color: rgba(0,0,0,.7)
}

.message.is-warning .message-body {
    border-color: #ffdd57;
    color: #3b3108
}

.message.is-danger {
    background-color: #fff5f7
}

.message.is-danger .message-header {
    background-color: #ff3860;
    color: #fff
}

.message.is-danger .message-body {
    border-color: #ff3860;
    color: #cd0930
}

.message-header {
    align-items: center;
    background-color: #4a4a4a;
    border-radius: 4px 4px 0 0;
    color: #fff;
    display: flex;
    font-weight: 700;
    justify-content: space-between;
    line-height: 1.25;
    padding: .75em 1em;
    position: relative
}

.message-header .delete {
    flex-grow: 0;
    flex-shrink: 0;
    margin-left: .75em
}

.message-header+.message-body {
    border-width: 0;
    border-top-left-radius: 0;
    border-top-right-radius: 0
}

.message-body {
    border-color: #dbdbdb;
    border-radius: 4px;
    border-style: solid;
    border-width: 0 0 0 4px;
    color: #4a4a4a;
    padding: 1.25em 1.5em
}

.message-body code,.message-body pre {
    background-color: #fff
}

.message-body pre code {
    background-color: transparent
}

</style>