requsetMapping可以修饰方法也可以修饰类
类定义了映射的初步信息，方法定义了具体信息【RUL】
requwstMapping(value,method,params,heads)
value == URL
method == POST/GET/PUT..
parmas和headers支持简单的表达式
	@RequestMapping(value="/ph",params={"username","age!=10"})
	public String testParamsAndHeader(){
		System.out.println("success");
		return "success";
	}
request映射表达式：(Ant风格的路径)
*：匹配任意多个字符

@pathvariable映射RUL绑定的占位符
@RequestMapping("/test/{id}")
	public String testPathVariable(@PathVariable("id") Integer id){
		System.out.println("test Variagle"+id);
		return "success";
	}

http://localhost:8080/SpringMVC1/test/33.do

REST：资源表现层状态转化，最流行的互联网软件构架
Resources：
@RequestMapping(value = "/testRequestParam")
	public String testRequestParam(
			@RequestParam(value = "username") String un,
			@RequestParam(value = "age", required = false, defaultValue = "0") int age) {
		System.out.println("testRequestParam, username: " + un + ", age: "
				+ age);
		return "success";
	}
获取请求参数，映射请求参数！！！！

@CookieValue

使用POJO对象绑定请求参数
此处有问题！！！
可以将Map和model和ModelMap类型数据作为目标方法的参数
	BindingAwareModelMap



@SessionAtributes可以放在类上边可以将数据放入其中，供多个类使用
@ModelAttribute 标记的方法会在被每个目标方法执行前被springMVC调用

fmt JSTL的国际化标签，需要在spring-mvc的配置文件中配置国际化资源文件

可以配置直接转发的页面,不需要handler的处理。
<mvc:view-Controller path="" view-name=""/>
注：在实际开发中通常都需要配置mvc:annotation-driven标签，否则


重定向：字符串中带有forward和redirectSpringMVC会对字符串特殊处理