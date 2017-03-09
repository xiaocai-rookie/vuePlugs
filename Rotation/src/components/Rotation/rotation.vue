<template>
	<div class="wrap">
		<div class="mobile-left" @click="mobileLeft">←</div>
		<div class="swiper" :style="{width:single+'px'}">
			<div class="swiper-wrap" :style="{width:wrapWidth,left:left+'px'}">
				<div class="swiper-main" v-for="main in mainList" :style="{width:single+'px'}">
					<h1>{{main.name}}</h1>
					<div class="main-list-wrap">
					<div v-for="(l,i) in main.list" @click="getCurrentIndex(i)" class="single-button">{{l}}</div>
					</div>
				</div>
			</div>
		</div>
		<div class="mobile-right" @click="mobileRight">→</div>
	</div>
</template>
<script>
	export default {
		name:"Rototion",
		props:{
			single:{
				type:Number,
				default:740
			},
			mainList:{
				type:Array
			},
			initIndex:{
				type:Number,
				default:0
			}
		},
		data:function(){
			return {
				useIndex:this.initIndex,
				left:-this.single*this.initIndex,
				leftTime:null,
				rightTime:null
			}
		},
		methods:{
			mobileLeft(){
				clearInterval(this.leftTime)
				if(this.useIndex === this.mainList.length-1){
					this.useIndex = -1;
					this.left = 0;
				}
				this.useIndex++;
				
				this.leftTime = setInterval(()=>{
					if(this.left <= -this.single*this.useIndex){
						clearInterval(this.leftTime)
						return false;
					}else{
						this.left += -20;
					}
				})
			},
			mobileRight(){
				clearInterval(this.rightTime)
				if(this.useIndex === 0){
					this.useIndex = this.mainList.length;
					this.left = -(this.useIndex-1)*this.single;
				}
				this.useIndex--;
				this.rightTime = setInterval(()=>{
					if(this.left >= -this.single*this.useIndex){
						clearInterval(this.rightTime)
						return false;
					}else{
						this.left -= -20;
					}
				})
			},
			getCurrentIndex(i){
				this.$emit("currentIndex",[this.useIndex,i])
			},
			modifyIndex(index){
				console.log(index);
				this.left = -this.single*index
			}
		},
		computed:{
			wrapWidth:function(){
				return (this.single*this.mainList.length)+"px";
			},
			setSwiperWidth:function(){
				return (this.single-40)+"px"
			},
		}
	}
</script>
<style scoped>
.swiper-main>h1{
	width:100%;
	text-align: center;
	padding:20px 0;
}
.wrap{
	margin:0 auto;
	overflow:hidden;
	position:relative;
}
.swiper{
	height:500px;
	overflow:hidden;
	float:left;
	position: relative;
	float:left;
}
.mobile-left{
	font-size: 40px;
	float:left;
	width:40px;
	height:500px;
	cursor: pointer;
	line-height: 500px;
}
.mobile-right{
	font-size: 40px;
	float:left;
	width:40px;
	height:500px;
	cursor: pointer;
	line-height: 500px;
}
.main-list-wrap{
	width:100%;
	background-color: green;
	height:500px;
}
.swiper-wrap{
	height:500px;
	position: absolute;
}
	
.swiper-main{
	height:500px;
	float: left;
	margin-top:20px;
}
.single-button{
	width:140px;
	height:140px;
	background-color:white;
	float:left;
	border-radius: 140px;
	text-align: center;
	line-height: 140px;
}
</style>