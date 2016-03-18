title: '地理定位的几种方式'
date: '2016-03-10'
categories:
	- '技术'
tags: 'html5, 定位'
---

<style>
	.table-mv
	{
		padding: 0;
		border-collapse: collapse;
	}
	.table-mv tr
	{
		border-top: 1px solid #cccccc;
		background-color: #fff;
		margin: 0;
		padding: 0;
	}
	.table-mv tbody tr td:first-child
	{
		width: 10%;
		font-weight: bold;
	}
	.table-mv tr:nth-child(2n)
	{
		background-color: #f8f8f8;
	}
	.table-mv tr th
	{
		font-weight: bold;
		border: 1px solid #cccccc;
		margin: 0;
		padding: 6px 13px;
	}
	.table-mv tr td
	{
		border: 1px solid #cccccc;
		margin: 0;
		padding: 4px 13px;
	}
	.table-mv tr th :first-child,
	.table-mv tr td :first-child
	{
		margin-top: 0;
	}
	.table-mv tr th :last-child,
	.table-mv tr td :last-child
	{
		margin-bottom: 0;
	}

	.bg-danger
	{
		background-color: #f25e3d;
	}

	.bg-success
	{
		background-color: #13BF13;
	}

	.color-warning
	{
		color: orange;
	}
</style>

很早就遇到过html5地理定位的问题，刚好看到这部分内容，总结记录，以下内容总结自《Head First HTML5 Programming》第五章，地理定位。

<!-- more -->

<h2>GPS</h2>
<table class="table-mv">
	<tbody>
		<tr>
			<td>定位方式</td>
			<td>GPS定位（全称 Global Positioning System）</td>
		<tr>
			<td>简介</td>
			<td>利用卫星提供极其精确的位置信息，位置信息可能包括高度、速度和朝向</td>
		</tr>
		<tr>
			<td>优点</td>
			<td>精确</td>
		</tr>
		<tr>
			<td>缺点</td>
			<td>1.设备必须能够看到天空； 2.可能花很长时间才能得到位置； 3.GPS定位比较耗电。</td>
		</tr>
		<tr>
			<td>备注</td>
			<td></td>
		</tr>
	</tbody>
</table>

<h2>IP地址</h2>
<table class="table-mv">
	<tbody>
		<tr>
			<td>定位方式</td>
			<td>IP地址</td>
		<tr>
			<td>简介</td>
			<td>使用一个外部数据库将IP地址映射到一个位置</td>
		</tr>
		<tr>
			<td>优点</td>
			<td>任何地方都可以使用</td>
		</tr>
		<tr>
			<td>缺点</td>
			<td>IP地址通常会解析为其他位置</td>
		</tr>
		<tr>
			<td>备注</td>
			<td>这种方法在城市级（有时在街区级）比较可靠</td>
		</tr>
	</tbody>
</table>

<h2>蜂窝电话</h2>
<table class="table-mv">
	<tbody>
		<tr>
			<td>定位方式</td>
			<td>蜂窝电话</td>
		<tr>
			<td>简介</td>
			<td>蜂窝电话三角定位可以根据你与一个或多个蜂窝电话基站的距离来确定你的位置（显然基站越多，位置就越精确）</td>
		</tr>
		<tr>
			<td>优点</td>
			<td>1.相当精确，在室内也能用； 2.比GPS快很多。</td>
		</tr>
		<tr>
			<td>缺点</td>
			<td>当你的位置特别偏僻，旁边只有一个基站的时候定位就不准确了</td>
		</tr>
		<tr>
			<td>备注</td>
			<td>这种方法在城市级（有时在街区级）比较可靠</td>
		</tr>
	</tbody>
</table>

<h2>Wi-Fi</h2>
<table class="table-mv">
	<tbody>
		<tr>
			<td>定位方式</td>
			<td>Wi-Fi</td>
		<tr>
			<td>简介</td>
			<td>Wi-Fi定位使用一个或多个Wi-Fi接入点完成三角定位。</td>
		</tr>
		<tr>
			<td>优点</td>
			<td>1.精确，在室内也能用； 2.速度快。</td>
		</tr>
		<tr>
			<td>缺点</td>
			<td>要求相对静止</td>
		</tr>
		<tr>
			<td>备注</td>
			<td></td>
		</tr>
	</tbody>
</table>

有这么多办法可以知道我们在哪里，但没办法知道我们的设备使用的是那种办法，因为要由浏览器来确定如何得到位置，不过浏览器可以从上述任何一种方法来确定我们的位置。

实际上，一个聪明的浏览器可能首先使用蜂窝电话三角定位，如果这种方法可行，你会得到一个大致的位置，然后再用Wi-Fi定位或GPS定位提供一个更精确的位置。

所以，我们不用担心位置如何确定，我们会把重点放到位置的精确度上，根据精确度能确定这个位置对我们有什么用。

<script>
	var bRs = document.getElementsByTagName('br');

	for (var i = bRs.length - 1; i >= 0; i--)
	{
		bRs[i].parentNode.removeChild(bRs[i]);
	}
</script>