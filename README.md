# AE2Web
AE animation is displayed on the web side

> #### 从AE到Web展示

###### 一、如何做到AE动效到Web显示？


- [x] 1.手工：通过掌握的Web技术；(效率较低，且还原难度较大)
- [x] 2.机械：通过工具进行导出；



**机械实现：**
1. **Bodymovin** 是 AE 的一个插件，用于将 AE 导出为 Web 动画（HTML、JSON、SVG 或 Canvas），仅支持 AE 部分特性。

2. **lottie-web** 是 Airbnb 团队的一个用于在 Web、Android、iOS 和 React Native 渲染 AE 动画的库。


**实现前准备步骤：**

1.下载安装AE，[下载地址](https://www.adobe.com/cn/products/aftereffects/free-trial-download.html)

2.下载Bodymovin插件

3.下载插件安装工具

4.制作AE动效或寻找合适的素材

[提取密码：aar7（插件+安装工具+素材）](https://pan.baidu.com/s/1bTRgWaZqdQYf79WPhJNGiA)

**导出步骤**

1.编辑 => 首选项 => 常规 => 允许脚本写入文件和访问网络

2.导入素材，窗口 => 扩展 => Bodymovin

3.选中文件 => Render => 导出素材（JSON+images文件夹）


**核心代码**

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8" />
		<title></title>
		<style type="text/css">
			#container{
				width: 300px;
				height: 600px;
			}
		</style>
	</head>
	<body>
		
		<!--容器-->
		<div id="container">
			
		</div>
		
		<script src="https://cdn.bootcss.com/bodymovin/4.13.0/bodymovin.min.js"></script>
		<script type="text/javascript">
			var animation = bodymovin.loadAnimation({
			  container: document.getElementById('container'), // Required
			  path: 'data.json', // Required
			  renderer: 'svg/canvas/html', // Required
			  loop: true, // Optional
			  autoplay: true, // Optional
			  name: "Hello World", // Name for future reference. Optional.
			})
		</script>
	</body>
</html>

```

