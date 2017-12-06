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