## 将时间戳格式化为字符串 （过滤器） ##


	Vue.filter('time', (timestamp)=>{
		if(!timestamp)return '';
		let date = new Date(timestamp);
		let y = date.getFullYear();
		let m = date.getMonth()+1;
		let d = date.getDate();
		// let h = date.getHours();
		// let min = date.getMinutes();

		if(m<10){
			m = '0'+m;
		}
		if(d<10){
			d = '0'+d;
		}

		return `${y}-${m}-${d}`;// ${h}:${min}
	});

## 把时间显示成`几分钟前`,`几小时前`
Safari的Date.parse方法不支持`2017-06-29 18:47:14`,需要转成`2017/06/29 18:47:14`
```
  var timeDuration = function (timeStr) {
    if (!timeStr || typeof timeStr != 'string') return;

    var curTime = Date.now();
    var pubTime = Date.parse(timeStr.split(" ")[0].split('-').join('/') + " " + timeStr.split(" ")[1]);
    var temp = curTime - pubTime;

    if (temp < 3600000) {
      return Math.floor(temp / 60000) + '分钟前';
    } else if (temp < 86400000) {
      return Math.floor(temp / 3600000) + '小时前';
    }
    return timeStr.split(" ")[0].split('-').join('/');
  }
```
