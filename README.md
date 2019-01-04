<h3>js模块插件</h3>
		<h4>包含四种：一个是通用工具，一个是DOM操作，一个是自动滚屏的跑马灯插件，以及一个ES6兼容垫片js(easyUtil.polyfill)，插件均支持模块化</h4>
		<h4>介绍（如无特殊说明，均以普通引用入口进行介绍，模块化以自定义为主）</h4>
		<h5>一、通用工具（easyUtil.common）普通引用通过符号_$或对象名easyUtil可以调取如下方法</h5>
		<ul>
			<li>
				<p>1.formatDate(date, fmt):</p>
				<p></p>&emsp;&emsp;日期格式化方法，第一参数为Date类型日期，第二参数为格式化的字符串，如“yyyy-MM-dd HH:mm:ss”</span>
			</li>
			<li>
				<p>2.formatJsonDate(jsonDate, fmt):</p>
				<p>&emsp;&emsp;json对象类型日期格式化方法，第一参数为json对象保存的日期，第二参数为格式化的字符串，如“yyyy-MM-dd HH:mm:ss”</p>
			</li>
			<li>
				<p>3.splitNumByThree(data, flag):</p>
				<p>&emsp;&emsp;千分位格式化数字方法，每三个为一组，逗号分隔，第一参数为数值，第二参数为是否间隔空格，选填，如“111, 222”，默认带空格，如不需要空格，则设为true即可</p>
			</li>
			<li>
				<p>4.currying(fn):</p>
				<p>&emsp;&emsp;函数柯里化</p>
			</li>
			<li>
				<p>5.bindCurry(fn, context):</p>
				<p>&emsp;&emsp;bind柯里化函数，第二参数为上下文</p>
			</li>
			<li>
				<p>6.scrollTogather(el_id1, el_id2, main_id):</p>
				<p>&emsp;&emsp;两个容器同步滚动方法，可用于对比场景，滚动其中一个，另一个也跟着滚动，参数分别为两个滚动容器的id和主容器id，如同一个页面存在多个该功能，建议每一组设置单独的主容器，防止出现干扰</p>
			</li>
			<li>
				<p>7.scrollUntilTop(eleId, container):</p>
				<p>&emsp;&emsp;滚动贴边方法，实现元素滚动到上边缘时，不再随父级滚动的功能，参数一为元素id选择器“#id”，参数二为父级元素id选择器（默认html为父级）</p>
			</li>
			<li>
				<p>8.switchAndAntiSql(data):</p>
				<p>&emsp;&emsp;防止sql注入，自动过滤sql关键字，如发现则返回false,否则返回URI编码后的字符</p>
			</li>
			<li>
				<p>9.testPalindrome(data):</p>
				<p>&emsp;&emsp;回文数判定方法，返回布尔值</p>
			</li>
			<li>
				<p>10.createProgress(done, total, {<br/>
						&emsp;el = document.body,<br/>
						&emsp;width = 200,<br/>
						&emsp;height = 10,<br/>
						&emsp;color = "green",<br/>
						&emsp;colorBg = "#000",<br/>
						&emsp;callback = function() {},<br/>
					} = {}) :</p>
				<p>&emsp;&emsp;canvas实现进度条功能，done为已完成数，total为总数，第三参数为可选，el为进度条插入元素位置，宽高，color进度条颜色，colorBg进度条背景颜色,callback为进度条结束时的回调函数</p>
			</li>
			<li>
				<p>11.switchPic(containerId, pics, {<br/>
		&emsp;speed = 1000,<br/>
		&emsp;width = 100,<br/>
		&emsp;height = 100,<br/>
		&emsp;callback = function(pic) {}<br/>
		&emsp;} = {}) :</p>
				<p>&emsp;&emsp;canvas实现切换图片，containerId为放置canvas容器Id，pics为图片src数组，第三参数为可选，speed为切换速度，图片显示宽高，callback为单击图片时的回调函数，参数为当前显示图片的src地址</p>
			</li>
			<li>
				<p>12.Cookie 读写或删除cookie的操作<br/>
				&emsp;Cookie.setCookie(key,value,expire_days = 7)<br/>
				&emsp;Cookie.getCookie(key)<br/>
				&emsp;Cookie.delCookie(key)<br/>			
			</li>
			<li>
				<p>13.uniqueArray(arr) <br/>
				&emsp;&emsp;数组去重方法, 返回去重后的数组<br/>		
			</li>
			<li>
				<p>14.getRootPath(flag) <br/>
				&emsp;&emsp;获取项目根路径方法，flag为是否获取带IP和端口号的根目录，默认不填即可<br/>		
			</li>
			<li>
				<p>15.getUrlParams(key) <br/>
				&emsp;&emsp;获取url参数，key为要获取的参数名，如不填写，则返回一个所有参数的对象集合<br/>		
			</li>
			<li>
				<p>16.MouseWheel 鼠标滚轮事件封装，兼容IE9及以上主流浏览器 <br/>
				&emsp;MouseWheel.on(callback, ele = "", flag = false):绑定事件，传入callback(event), ele为目标id选择器#+"XX"，不填写则默认监听document，flag为事件处理阶段，默认false为冒泡阶段<br/>
				&emsp;MouseWheel.off() 取消事件<br/>
				&emsp;MouseWheel.delta(event) 获取鼠标滚动delta值，统一为向上120，向下-120<br/>		
			</li>
		</ul>
		<h5>二、DOM工具（easyUtil.dom）普通引用通过对象名easyDOM点出如下方法,该模块适用原生js操作</h5>
		<ul>
			<li>
				<p>1.ready(function(){}):</p>
				<p></p>&emsp;&emsp;DOM加载完毕调用函数，easyDOM.ready(function(){})用于在DOM结构加载完毕后执行脚本</span>
			</li>
			<li>
				<p>2.$(selector):</p>
				<p></p>&emsp;&emsp;选中单个DOM元素，传入相应的selector</span>
			</li>
			<li>
				<p>3.$$(selector):</p>
				<p></p>&emsp;&emsp;选中多个DOM元素，传入相应的selector</span>
			</li>
			<li>
				<p>4.addClass(el, ...classes)(classList方法的兼容方法):</p>
				<p></p>&emsp;&emsp;增加class类样式，el为节点对象，classes类可以写多个，以逗号分隔的字符串即可，元素已有的类自动忽略</span>
			</li>
			<li>
				<p>5.removeClass(el, ...classes)(classList方法的兼容方法):</p>
				<p></p>&emsp;&emsp;删除class类样式，el为节点对象，classes类可以写多个，以逗号分隔的字符串即可，元素没有的类自动忽略</span>
			</li>
			<li>
				<p>6.toggleClass(el, class_name)(classList方法的兼容方法):</p>
				<p></p>&emsp;&emsp;切换class类样式，el为节点对象，实现添加或删除class_name功能</span>
			</li>
			<li>
				<p>7.forEach(els,fn):</p>
				<p></p>&emsp;&emsp;浏览器兼容forEach的方法，传入节点对象集合els,和自定义自定义循环回调函数fn， fn函数参数为item, index</span>
			</li>
			<li>
				<p>8.style(el,key,value):</p>
				<p></p>&emsp;&emsp;获取或赋值给对应的style属性，key值可直接输入对应的css属性（无需驼峰转换），value值有则赋值，无则取值</span>
			</li>
			<li>
				<p>9.attr(el,key,value):</p>
				<p></p>&emsp;&emsp;DOM属性的取值或赋值方式，key为对应的DOM属性，无需关注是否DOM对象的属性，还是自定义属性，该方法均可操作，value值有则赋值，无则取值</span>
			</li>
		</ul>
		<h5>三、跑马灯插件（easyUtil.Scrolling）普通引用通过对象名Scrolling点出如下方法</h5>
		<ul>
			<li>
				<p>easyScroll(id, speed):</p>
				<p>&emsp;&emsp;传入滚动主容器Id和滚动的速度，默认100ms</p>
			</li>
		</ul>
		<h5>四、兼容垫片js(easyUtil.polyfill)。直接将文件引入，然后正常使用对应的方法即可</h5>
				<p>&emsp;1. 兼容一些ES6新添加的数组，对象方法，也提供一些数组forEach等方法对IE8的兼容</p>
				<p>&emsp;2. 兼容IE8及以下js数组等方法的使用</p>
				<p>&emsp;3. 与其他文件无冲突</p>
		<ul>
			<li>
				<p>提供的兼容方法如下（兼容IE8及以下）:</p>
				<p>Array.prototype.forEach</p>
				<p>Array.prototype.map</p>
				<p>Array.prototype.reduce</p>
				<p>Array.prototype.filter</p>
				<p>Array.prototype.every</p>
				<p>Array.prototype.some</p>
				<p>Array.from</p>
				<p>Array.of</p>
				<p>Array.prototype.findIndex</p>
				<p>Array.prototype.find</p>
				<p>Object.is</p>
				<p>requestAnimationFrame/cancelAnimationFrame</p>				
			</li>
		</ul>
