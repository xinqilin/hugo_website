---
title: "Vue Intro"
author: Bill.Lin
date: 2021-07-04T22:27:03+08:00
draft: false
tags: []
Description: ""
Categories: ["Vue"]
DisableComments: false
---

# 筆記 Vue 未整理 version

vetur
vue2 snippets
chrome: vue plugin


單向綁定
v-text v-html
v-bind:href="link"   vue instance 內的 method 的 data:{link}
(v-bind:href 可縮寫:href)

雙向綁定
v-model

綁定事件
v-on:click="num++"   =   @click

v-on 防止事件冒泡{
`.stop`: 阻止事件冒泡倒父層 
`.prevent`: 阻止默認(預設) 事件發生
`.capture`: 阻止事件捕獲模式
`.self`: 只有自身觸發事件才執行
`.once`: 只執行一次
}

按鍵修飾符 v-on:keyup.13
13 是鍵碼
v-on 按鍵修飾符 懶人包{
`.enter`
`.tab`
`.delete`
`.esc`
`.space`
`.up`
`.down`
`.left`
`.right`
}


v-for

v-for="user in users"  或 v-for="(user, index) in users"
v-for="(value, key, index) in users"  {{value}} {{key}} {{index}}
 
v-for 增加 :key = ""  可增加效率 最主要是是別惟一值 :key 是 v-bind縮寫

v-if  裡面都填boolean
整個標籤不見
v-show  裡面都填boolean
是用 display:none


常跟 v-if 一起用
v-else-if
v-else 



computed 計算屬性
watch 監控屬性
filter 過濾屬性  -> 使用 {{user.gender | genderFilter}}

```js

new Vue({
	el: "#app",
	data:{
		a:100,
		b:200
	},
	computed: {
		total: function(){
			return this.a+this.b
		}
	},
	watch:{
		a: function(newValue, oldValue){
			alert("new: "+newValue+" , old: "+oldValue)
			if(a>3){
				this.msg = "太多"
			}
		}
	},
	filters:{
		genderFilter(val){
			if(val == 1) return "male"
			else return "female"
		}
	}
	
})

```

組件: 

```js

<script>

	Global 組件:
	Vue.component("counter",{
		template: `<button v-on:click = "count++"> {{count}}</button>`
		data(){
			return {
				count: 0
			}
		}
	});
	
	區域組件:
	const buttonCounter = {
		template: `<button v-on:click = "count++"> {{count}}</button>`
		data(){
			return {
				count: 0
			}
		}
	}
	後 放入 vue instance components:{}中
	
	components:{
		'button-counter 名字': buttonCounter
	}
	
	```
	<button-counter></button-counter> 使用
	```
	
</script>

```

