requsetMapping�������η���Ҳ����������
�ඨ����ӳ��ĳ�����Ϣ�����������˾�����Ϣ��RUL��
requwstMapping(value,method,params,heads)
value == URL
method == POST/GET/PUT..
parmas��headers֧�ּ򵥵ı��ʽ
	@RequestMapping(value="/ph",params={"username","age!=10"})
	public String testParamsAndHeader(){
		System.out.println("success");
		return "success";
	}
requestӳ����ʽ��(Ant����·��)
*��ƥ���������ַ�

@pathvariableӳ��RUL�󶨵�ռλ��
@RequestMapping("/test/{id}")
	public String testPathVariable(@PathVariable("id") Integer id){
		System.out.println("test Variagle"+id);
		return "success";
	}

http://localhost:8080/SpringMVC1/test/33.do

REST����Դ���ֲ�״̬ת���������еĻ������������
Resources��
@RequestMapping(value = "/testRequestParam")
	public String testRequestParam(
			@RequestParam(value = "username") String un,
			@RequestParam(value = "age", required = false, defaultValue = "0") int age) {
		System.out.println("testRequestParam, username: " + un + ", age: "
				+ age);
		return "success";
	}
��ȡ���������ӳ�����������������

@CookieValue

ʹ��POJO������������
�˴������⣡����
���Խ�Map��model��ModelMap����������ΪĿ�귽���Ĳ���
	BindingAwareModelMap



@SessionAtributes���Է������ϱ߿��Խ����ݷ������У��������ʹ��
@ModelAttribute ��ǵķ������ڱ�ÿ��Ŀ�귽��ִ��ǰ��springMVC����

fmt JSTL�Ĺ��ʻ���ǩ����Ҫ��spring-mvc�������ļ������ù��ʻ���Դ�ļ�

��������ֱ��ת����ҳ��,����Ҫhandler�Ĵ���
<mvc:view-Controller path="" view-name=""/>
ע����ʵ�ʿ�����ͨ������Ҫ����mvc:annotation-driven��ǩ������


�ض����ַ����д���forward��redirectSpringMVC����ַ������⴦��