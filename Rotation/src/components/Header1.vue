<template>
	 <div class="header">
	 	
	 	 <Rotation-box class="test-rotation" 
	 	 :mainList="testData" 
	 	 v-on:currentIndex="getIndex"
	 	 :initIndex="4"
	 	 ></Rotation-box>
	 </div>
</template>
<script type="text/javascript">
	import Vue from "vue";
	import Rotation from "./Rotation";
	Vue.use(Rotation);
	export default{
	   name:'header1',
	   data:function(){
	   	return{
		   	todos: [ 
		      { text: 'Learn JavaScript' },
		      { text: 'Learn Vue' },
		      { text: 'Build something awesome' }
		    ],
		    testData:[
					{
						name:"第一序列",
						list:["按钮1","按钮2","按钮3","按钮4","按钮5"]
					},
					{
						name:"第二序列",
						list:["按钮1","按钮2","按钮3"]
					},
					{
						name:"第三序列",
						list:["按钮1","按钮2","按钮3","按钮4"]
					},
					{
						name:"第四序列",
						list:["按钮1","按钮2","按钮3","按钮4","按钮5"]
					},
					{
						name:"第五序列",
						list:["按钮1","按钮2"]
					},
					{
						name:"第六序列",
						list:["按钮1","按钮2"]
					},
					{
						name:"第七序列",
						list:["按钮1","按钮2"]
					},
					{
						name:"第八序列",
						list:["按钮1","按钮2"]
					}
				],
	   	}
	   },
	   methods:{
	   	getIndex(index){
	   		console.log(index)
	   	}
	   }
	}
</script>
<style scoped>
.test-rotation{
	margin:0 500px;
}	
</style>