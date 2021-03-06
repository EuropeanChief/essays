# spring学习之DI一

## 一.依赖和依赖注入

### 1.依赖注入有三种方法
1).构造器注入

 构造器注入是通过配置构造器参数实现，有构造器方法、静态工厂方法、实例工厂方法。具体细节上节有说明。这里要加个小细节，就是静态工厂方法中使用的方法必须是用static标识的静态方法不然会报错。

a.根据参数索引注入

 index指的是第几个参数，如果你的方法中具有多个参数，就一定要小心对应index的位置，我之前有个错误，就是写value值是没注意对应index，导致参数类型不一致一直在报错。
```
    <bean id="byIndex" class="test.HelloImpl2">
        <constructor-arg index="0" value="0" />
        <constructor-arg index="1" value="HelloImpl2_0" />
    </bean>
```

b.根据参数类型注入

 type指定参数类型，如果是基本类型可以直接在type里写，如type="int"，如果不是就需要指定类，如：type="java.lang.String"
```
    <bean id="byType" class="包名.类名" >
        <constructor-arg type="int" value="0" />
        <constructor-arg type="java.lang.String" value="111" />
    </bean>
```

c.根据参数名注入
    name指定形参名，value参数值。
```
    <bean id="byName" class="包名.类名">
        <constructor-arg name="ind" value="1" />
        <constructor-arg name="mess" value="2222" />
    </bean>
```

2).setter注入

 当你使用的类中不含有构造函数时，创建setter方法就能进行setter注入，当你的类中含有其他构造函数时，必须保证有空构造函数，否则无法进行setter注入。
 xml文件中代码
```
    <bean id="A" class="test.AImpl">
        <property name="message" value="A" />
        <property name="index" value="0" />
    </bean>
```
 AImpl类中代码
```
    private String message;
    private int index;
    
    public String getMessage() {
        return message;
    }

    public void setMessage(String message) {
        this.message = message;
    }

    public int getIndex() {
        return index;
    }

    public void setIndex(int index) {
        this.index = index;
    }

    @Override
    public void sayHello() {
        System.out.println(index+" "+message);
    }

```

 测试类中代码
```
ApplicationContext DI = new ClassPathXmlApplicationContext("/test/hello_DI.xml");
HellowApi A = DI.getBean("A", HellowApi.class);
A.sayHello();
```

3).方法注入

    因为Spring对于boolean类型进行了容错处理，可以使用"true/false"标准的java值进行注入，还能使用"yes/no"、"on/off"、"1/0"进行注入。

a.注入Bean ID

