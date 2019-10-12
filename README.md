# IAM1.0  指令驱动模型</br>

设计理念:</br> 对象可以通过指令的方式向服务商请求任何数据，操作者不再考虑返回值的类型问题，这个问题交给具体方法</br></br>
核心思想:</br>
     实现请求方，操作方和返回方的解耦，一个对象可以通过改变指令从服务商获取任何类型的返回数据，指令决定具体操作，操作决定返回类型。</br></br>
具体流程:</br>
  一个携带request字段的对象交给事先填充过操作对象的容器，然后容器调用对应操作对象的对应方法，返回对应的返回值。</br>
这一过程中，操作者并没有请求者的引用，也没有返回值的引用</br></br>
实用之处:</br>前端后台数据交互，解决请求参数和返回数据  之间接口复杂的问题，，实现了想请求什么数据就会获得什么数据的灵活性，并且面向对象，解析简单
</br></br>
	
Test 相见test</br>

         	Context context=Context.getContext();
		context.addTranDataMap(TestCome.class,TestBack.class);
		context.addActor(TestActor.class);
		context.showWorks();
		TestCome comeData=new TestCome();
		comeData.setType("test");
		comeData.setAction("test");
		TestBack backData=context.back(comeData);
		System.out.println(backData.getData());
		
		
		
</br>
<h1>IAM-IOTB 2.0</h1>
<p>
	2.0 改变指令的形式为request</br>取消了Come对象中构造方法的限制</br取消Come和Back成对的限制</br取消添加对象class的繁琐,
	只提供添加actor</br增强actor中方法的作用，使返回值可以为任意类型
	
</p>
