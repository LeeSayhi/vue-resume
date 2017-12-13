<template>
	<div>
		<div id="app" class="showCode">
			<pre>
				{{code}}
			</pre>
	  </div>
	  <div class="styleCode" v-html="styleCode"></div>
	</div>
</template>

<script>

export default {
	data () {
		return {
			code: '',
			style: `
/*
* 你好哇，
* 我叫赵力，今年25，是个coder,
* 开始变身啦~巴啦啦~~
*/

/* 首先给所有元素加上过渡效果 */
* {
	transition: all .3s
}
/* 然后改背景色 */
body {
	background: red;
}
/* 红色太丑，再变 */
body {
	background: rgb(0,43,54); color: rgb(222,222,222)
}
/* 文字离边框太近了 */
.showCode {
	padding: .5em;
	border: 1px solid;
	margin: .5em;
	overflow: auto;
	width: 45vm;
	height: 90vh;
}
/* 再加点3D效果呗 */
html {
	perspective: 1000px
}
.showCode {
	position: fixed;
	left: 0;
	top: 0
	-webkit-transition: none;
	transition: none;
	-webkit-transform: rotateY(10deg) translateZ(-100px);
	transform: rotateY(10deg) translateZ(-100px)
}
`
		}
	},
	created () {
		let i = 0
		setInterval(() => {
			this.code = this.style.substring(0, i)
			i += 1
		}, 50)
	},
	computed: {
		styleCode () {
			return `<style>${this.code}</style>`
		}
	}
}
</script>

<style>
</style>
