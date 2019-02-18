1.RN开发文档：React Native 中文
2.配置环境变量
3.windows中可以配置nrm 方便切换，  命令： nrm ls   nrm use  







对于RN中，如果需要使用tab-bar，可以使用github上面的react-nvative-tab-navigator  就是一下页面的下面的切换栏



RN中使用icon  github : react-native-vector-icons

然后需要修改一些配置，应该直接使用 react-native link 就可以直接配置其中的内容。



RN中使用轮播图，组件： react-native-swiper



RN中使用路由：组件 react-native-router-flux



RN中使用调用拍照功能的组件 ： react-native-image-picker



RN中弹框组件： react-native-easy-toast



RN中checkbox组件： react-native-check-box



RN中实现拖拽的组件： react-native-scrollable-listview



RN中实现滑动出现标题的组件： react-native-parallax-scroll-view





使用RN中的组件：Navigator，只需要从RN中import就可以，然后再主页面中引入，到组件中的时候，将navigator也传递过去，那么组件中就可以使用这个路由对象，实现路由。

因为使用navigator，定义了默认的路由，就是第一个路由，然后并且获取到路由之后，定义了<Component 并且将navigator这个对象传递到路由过去的组件中，在组件中才可以使用this.props.navigator.pus()或者this.props.nvavigator.pop()等操作，并且将路由的参数等一起传递过去。



下级页面向上级页面传递数据的时候，可以使用回调函数，触发上级页面中定义的回调函数，然后就可以向上级页面传递数据。





可以使用FlatList组件的下拉刷新和延迟加载等功能，

如果使用原生的加载的功能：

​    <FlatList 

​            data={this.state.dataArray},

​	    renderItem={(data)=>this.renderItem(data)},

​	     refreshing={this.state.isLoading},

​	     onRefresh={()=>{this.loadData}}

​		/>

如果不想使用其中的原生的加载功能：使用react-native中的RefreshControl

​             <FlatList 

​          	  data={this.state.dataArray},

​	  	  renderItem={(data)=>this.renderItem(data)},

​	   	 refreshControl={

​				<RefreshControl

​					title={"Loading"},

​					colors={['red']},   ---andriod

​					tintColor={'orange'}, ---ios

​					titleColor={'red'},

​					refreshing={this.state.isLoading},

​					onRefresh={()=>this.loadData()}					

​			}

​		/>







RN中，使用<Image/> 标签，如果使用的是网络的图片，如果没有设置height 和width，则不会显示图片，如果使用的是本地的图片，则可以正常显示。





RN中如果需要单击<Text>标签中的内容，可以使用<TouchableOpacity onPress={()=>{}} >标签，可以使用里面的onPress属性





