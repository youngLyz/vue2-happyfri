<template>
	<transition 
		name="custom-classes-transition"
		enter-active-class="animated flipInX"
		leave-active-class="animated bounceOutDown">
		<div class="modal is-active" v-show="showModal">
		  <div class="modal-background"></div>
		  <div class="modal-content">
		  	<div class="box">
		  		<slot></slot>	
		  	</div>	    
		  </div>
		  <button @click="handleModalClose" class="modal-close is-large" aria-label="close"></button>
		</div>
	</transition>
</template>

<script type="text/javascript">
	export default {
		name: 'modal',
		props:{
			showModal: Boolean
		},
		methods: {
			handleModalClose () {
				this.$emit('closeModal',false);
			}
		}
	}
</script>

<style scoped>

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

.modal,.modal-background {
	bottom: 0;
    left: 0;
    position: absolute;
    right: 0;
    top: 0;
}
.modal {
    align-items: center;    
    flex-direction: column;
    justify-content: center;
    overflow: hidden;
    position: fixed;
    z-index: 40
}
.modal.is-active {
    display: flex
}

.modal-background {
    background-color: rgba(10,10,10,.86)
}

.modal-card,.modal-content {
    margin: 0 20px;
    max-height: calc(100vh - 160px);
    overflow: auto;
    position: relative;
    width: 100%;
}
.box {
    background-color: #fff;
    border-radius: 6px;
    box-shadow: 0 2px 3px rgba(10,10,10,.1), 0 0 0 1px rgba(10,10,10,.1);
    color: #4a4a4a;
    display: block;
    padding: 1rem;
    font-size: 16px;
}
@media screen and (min-width: 769px),print {
.modal-card,.modal-content {
        margin:0 auto;
        max-height: calc(100vh - 40px);
        width: 640px
    }
}

.modal-close {
    background: 0 0;
    height: 40px;
    position: fixed;
    right: 20px;
    top: 20px;
    width: 40px
}

.modal-card {
    display: flex;
    flex-direction: column;
    max-height: calc(100vh - 40px);
    overflow: hidden
}

.modal-card-foot,.modal-card-head {
    align-items: center;
    background-color: #f5f5f5;
    display: flex;
    flex-shrink: 0;
    justify-content: flex-start;
    padding: 20px;
    position: relative
}

.modal-card-head {
    border-bottom: 1px solid #dbdbdb;
    border-top-left-radius: 6px;
    border-top-right-radius: 6px
}

.modal-card-title {
    color: #363636;
    flex-grow: 1;
    flex-shrink: 0;
    font-size: 16px;
    line-height: 1
}

.modal-card-foot {
    border-bottom-left-radius: 6px;
    border-bottom-right-radius: 6px;
    border-top: 1px solid #dbdbdb
}

.modal-card-foot .button:not(:last-child) {
    margin-right: 10px
}

.modal-card-body {
    -webkit-overflow-scrolling: touch;
    background-color: #fff;
    flex-grow: 1;
    flex-shrink: 1;
    overflow: auto;
    padding: 20px
}
</style>