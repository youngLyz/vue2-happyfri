<template>
  	<div>
  		<task>this is a task</task>
  		<task></task>       
      <slot-comp>    	 	
		      <h1 slot="header">Here might be a page title</h1>		  	
		   	  <p>A paragraph for the main content.</p>
			     <p>And another one.</p>
			     <p slot="footer">Here's some contact info</p>			
      </slot-comp>
        
        <button class="button" @click="handleShowMsg">show message</button>
        <message class="message" :isVisiable="isVisiable" @changeShow="changeMsgShow">
        	<template slot="title">欢迎</template>
        	<div slot="content">你好，vue</div>
        </message>
        
        <button class="button" @click="handleShowModal">show modal</button>
        <modal :showModal="showModal" @closeModal="closeModalShow">
            <template>
              <strong>John Smith</strong> <small>@johnsmith</small> <small>31m</small>
              <br>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean efficitur sit amet massa fringilla egestas. Nullam condimentum luctus turpis.
            </template>
        </modal>
        <zentabs>
          <tab name="图片" :selected="true" :key="tab1">
            这是图片内容
          </tab>
          <tab name="音乐" :key="tab2">
            这是音乐内容
          </tab>
          <tab name="文档" :key="tab3">
            这是文档内容
          </tab>
          <tab name="视频" :key="tab4">
            这是视频内容
          </tab> 
        </zentabs>

        <comment v-model="comment"></comment>
    </div>
</template>

<script>
import task from '../components/task'
import slotComp from '../components/slot'
import message from '../components/message'
import modal from '../components/modal'
import zentabs from '../components/zentabs'
import tab from '../components/tab'
import comment from '../components/comment'

export default {
	name: 'indexPage',
  data () {
    return {
      isVisiable: false,
      showModal: false,
      comment: ''
    }
  },
  components: {
  		task,
  		slotComp,
  		message,
      modal,
      zentabs,
      tab,
      comment
  	},
    methods: {
      handleShowMsg () {
        this.isVisiable = true;
      },
      handleShowModal () {
        this.showModal = true;
      },
      changeMsgShow (isShow) {
        this.isVisiable = isShow;
      },
      closeModalShow (isShow) {
        this.showModal = isShow;
      }
    },
    created(){
        
    }
}
</script>

<style lang="less" scoped>
  body{
    background: none !important;
  }
  .button{
    width:80%;
    height:45px;
    margin:15px 10%;
  }
</style>
