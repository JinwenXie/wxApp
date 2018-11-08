## 小程序学习流水账<br>

### 2018-11-08<br>
##### 小程序内部跳转页面传参：<br>
**当前wxml文件:**<br>
`<view bindtap="goOtherPage" data-argument="1"></view>`<br>
**当前js文件:**<br>
	goOtherPage: function(event){<br>
	  var agt = event.currentTarget.dataset.argument;// 使用该方法可以获取到当前标签上的自定义属性argument值<br>
	  wx.navigateTo({<br>
	       url: 'test?argument=' + agt<br>
	  })<br>
	}<br>

**跳转的js文件:**<br>
	Page({<br>
		onLoad: function(option){<br>
			console.log(option.argument)<br>
		}<br>
	})<br>