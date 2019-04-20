# echarts
echarts笔记

>  折线图

![image](https://github.com/Chencb1991/echarts/blob/master/%E8%BF%9B%E5%87%BA%E9%87%91%E9%A2%9D%E7%BB%9F%E8%AE%A1%20(2).png)

```
<!-- 为 ECharts 准备一个具备大小（宽高）的 DOM -->
<div id="main" style="height:400px;width:100%"></div>

// 基于准备好的dom，初始化echarts实例
        var myChart = echarts.init(document.getElementById('main'));
        var option = {
		    title: {
		        text: '进出金额统计'
		    },
		    tooltip: {
		        trigger: 'axis'
		    },
		    legend: {
		        data:['放款金额','还款金额']
		    },
		    grid: {
		        left: '3%',
		        right: '4%',
		        bottom: '15%',
		        containLabel: true
		    },
		    toolbox: {
		        feature: {
	            dataZoom: {
	                yAxisIndex: 'none'
	            },
	            restore: {},
	            saveAsImage: {}
	        }
		    },
		    dataZoom: [
		        {
		            show: true,
		            realtime: true,
		            //bottom:-15,
		            start: 50,
		            end: 100  
		        },
		        {// 这个dataZoom组件，默认控制x轴。
		            type: 'inside', // 这个 dataZoom 组件是 slider 型 dataZoom 组件
		            realtime: true,
		            start: 50,// 左边在 10% 的位置。
		            end: 100// 右边在 60% 的位置。
		            
		        }
		    ],//底部滑动缩放
		    xAxis: {
		        type: 'category',
		        boundaryGap: false,
		        axisLine: {onZero: false},
		        data: ['11-11','11-12','11-13','11-14','11-15','11-16','11-17']
		    },  //x
		    yAxis: {
		        type: 'value'
		    },
		    series: [
		        {
		            name:'放款金额',
		            type:'line',
		            stack: '总量',
		            itemStyle:{  
	                     normal:{  
	                            lineStyle:{  
	                                color:'#FB6F51'  
	                            }  
	                        }  
	                    }, //折线颜色
		            data:[51200, 13020, 1001, 13400, 900, 2300, 61000]
		        },
		        {
		            name:'还款金额',
		            type:'line',
		            stack: '总量',
		            itemStyle:{  
	                     normal:{  
	                            lineStyle:{  
	                                color:'#070707'  
	                            }  
	                        }  
	                    },  //折线颜色
		            data:[25200, 1820, 1910, 62340, 2900, 33000, 3100]
		        }
		    ]
		};

		 // 使用刚指定的配置项和数据显示图表。
        myChart.setOption(option);
  ```
  
  
  
  
  
