<template>
	<div id="app">
		<mine-sweeping 
			v-if="showGame"
			:show-game.sync="showGame"
			:game-info="gameInfo"
			></mine-sweeping>
		<select-level 
			v-else 
			@chose-level="choseLevel"></select-level>
	</div>
</template>

<script>
import SelectLevel from "@/components/SelectLevel.vue";
import MineSweeping from "@/components/MineSweeping.vue";
export default {
	name: "app",
	components: { 
		SelectLevel,
		MineSweeping 
	},
	data() {
		return {
			// 是否展示游戏盘
			showGame: true,
			// 游戏盘格子数和雷数
			gameInfo: [8, 8, 10]
		}
	},
	methods: {
		// 选择难度
		choseLevel(level) {
			this.gameInfo = level;
			this.showGame = true;
		}
	}
}
</script>	


<style lang="scss">
html, body, #app{
	height: 100%;
}
#app {
	position: relative;
	top: 0;
	bottom: 0;
	font-family: "Avenir", Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
}
ul {
	padding: 0;
	list-style: none;
}
</style>
