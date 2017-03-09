# vue2

> vue2 demo

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# 参数说明:
## initIndex 初始化开始的页码
## mainList 生成DOM的数据 必传
## 格式如下:
```
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
```
# v-on:currentIndex="" 获取内部点击的是哪一个 返回的是一个 两个元素的集合  
## 第二个是当前页的index 第一个是 页的index 
# 第一个写组件 有什么 不对的地方欢迎指正 这个组件待完善的地方 还有很多 如果能够添加代码 感激不尽
# 如果要从外部设置 页的index 可以使用 $refs 调用modifyIndex（）方法 传入index 即可