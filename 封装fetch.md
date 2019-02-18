封装fetch



export default class HttpUtil{

​	static get(url){

​		return new Promise(resolve,reject)=>{

​			fetch(url)

​				.then(response =>response.json())

​				.then(result =>{

​					resolve(result)

​			})

​				.catch(error=>{

​					reject(error)

​			})

​		})

​	}



​	static post(url,data){

​		return new Promise((resolve,reject)=>{

​			fetch(url,{

​				method:'POST',

​				header:{

​					'Accpet':'application/json',

​					'Content-Type':'application/json'​				

​				},

​				body:JSON.stringify(data) 

​			}) 

​			.then(response =>response.json())

​				.then(result =>{

​					resolve(result)

​			})

​				.catch(error=>{

​					reject(error)

​			})

​		})

​	}

} 

如何调用，直接import

然后

​     HttpUtil.get(url)

​		.then(result=>{

​			//将获取到的result转换为json字符串

​			this.setState({result.JSON.stringify(result)})

​		})







如果需要存储的话，可以使用AsyncStroage



AsyncStroage.setItem('key',this.text,(error)={

​	if(!error){

​		this.toast.show('保存成功')

​	}else{

​		this.toast.show('')

​	}

})



AsyncStorage.getItem(KEY,(error,result)=>{

​	if(!error){

​		this.toast.show('取出'+result)

​	}

})





Textinput 可以使用属性， onChangeText={text=>this.text=text}





 使用Toast,react-native-easy-toast

