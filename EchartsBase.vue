<template>
	<!-- 为 ECharts 准备一个具备大小（宽高）的 DOM -->
	<div id="base" style="width: 600px;height:400px;"></div>  
</template>

<script>
	export default {
		methods: {
			showEcharts() {
				let echarts = this.$echarts;
				// 获取echarts的实例对象（echarts通过初始化，获取实例对象。基于准备好的dom，初始化echarts实例）
				let myChart = echarts.init(document.getElementById('base'));

				// 配置项（指定图表的配置项和数据）
				let option = {
                    // 标题组件(对象)，包含主标题和副标题。
					title: {
						text: 'ECharts 入门示例3'
                    },
                    // 提示框组件(对象)，即鼠标移上去显示的提示信息。
                    tooltip: {},
                    // 图例组件（图例组件展现了不同系列的标记(symbol)，颜色和名字。可以通过点击图例控制哪些系列不显示。）
					legend: {
						data: ['销量3']
                    },
                    // X 坐标轴(对象)
					xAxis: {
						data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
                    },
                    // Y 坐标轴(对象)
					yAxis: {
                    },
                    // 系列列表（系列列表。每个系列通过 type 决定自己的图表类型：柱状bar、饼状pie、折线line 等）
					series: [{
						name: '销量3',
						type: 'bar',    // 柱状图
						data: [5, 20, 36, 10, 10, 20]   // 柱状图 显示的值
					}]
				};

				// 使用刚指定的配置项和数据显示图表。
				myChart.setOption(option);
			}
		},
		mounted() {
			this.showEcharts()
		}
	}
</script>

<style>

</style>