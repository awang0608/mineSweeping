<template>
    <div class="main">
		<div>选择难度</div>
		<ul>
			<li v-for="(item, index) in level" :key="index" @click="handleChoseLevel(item.value)">{{ item.text }}</li>
		</ul>
    </div>
</template>

<script>
export default {
	name: "index",
	components: { },
	data() {
		return {
			// 难度
			level: [
				{
					text: '青铜', // 难度描述
					value: [9, 9, 10] // 格子横排数，格子纵排数，雷数
				}, {
					text: '黄金',
					value: [12, 9, 20] 
				}, {
					text: '钻石',
					value: [16, 9, 30]  
				}, {
					text: '星耀',
					value: [16, 16, 50]  
				}, {
					text: '王者',
					value: [30, 16, 99]  
				}
			]
		}
	},
	methods: {
		// 选择难度
		handleChoseLevel(level) {
            this.$emit("chose-level", level);
		}
	}
};
</script>
<style lang="scss" scoped>
.main {
    margin: 0 auto;
	padding: 10px;
    position: relative;
    top: 50%;
    transform: translateY(-50%);
	border: 2px dashed #0b7777;
    border-radius: 5px;
	width: 50%;
	font-size: 18px;
	text-align: center;
	color: #0b7777;
	ul {
		li {
			margin: 10px 0;
			cursor: pointer;
		}
	}
}
</style>
