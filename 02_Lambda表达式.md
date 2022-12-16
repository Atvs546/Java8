# 1.为什么要使用Lambda表达式?

Lambda是一个匿名函数，我们可以把Lambda表达式理解为是一段可以传递的代码，可以写出更简洁，更灵活的代码，作为一种更紧凑的代码风格，使Java语言的表达能力得到提升

# 2.Lambda表达式的初步认识

创建一个接口，接口中定义一个save方法，如果需要在方法中编写具体的内容，可以通过接口的匿名类以及中括号对接口中的方法进行完善,例如有一个save接口，save接口中有一个dosave方法

```java
save(参数1，参数2){
@Overrvide
public  void  dosave(){
//完善方法
System.out.println("正在save.....");
}
}
```

对于Lambda的使用调用匿名类，

例如，以这个匿名类作为参数

dohello  doh=new  dohello((e)->e.save)

# 3.Lambda表达式的基础语法

在java8中引入一个新的操作符"->"该操作符成为箭头操作符或Lambda操作符

左侧:Lamb表达式的接口中方法的参数列表

右侧:Lambda表达式中所需要执行的功能，即Lambda体

## 1.无参数无返回值

()->System.out.printlnm("hello");

```
 //通过匿名类对象的方式进行创建对象,Runnable是一个接口
        Runnable ru=()->System.out.println("hello");
```

Runnable是接口，因为这个没有参数的，所以"->"左边是没有东西的,右边就是要执行的内容

在->符号中，如果要使用当前类中的变量在jdk1.7以前需要用finally声明

## 2.有一个参数并且无返回值

语法：(x)->System.out.println("helllo");,只有一个参数时，小括号可以省略

Consumer接口中的acept方法就是一个有一个参数且无返回值的一个方法

Consumer<String> con=(x)->System.out.println("开始执行");

声明Consumer对象"->"左边就是需要acept需要的参数,“->"右边就是在acept方法中需要执行的内容,

调用acept方法,con.acept("尚硅谷")；。该方法执行依然需要传入参数



## 3.有两个参数，有返回值

如果有多条语句，"->"一定要使用大括号,，若只有return一条语句，"{}"和return都可以不写

语法:(x,y)->{

System.out.pringtln('hello"');

return   Integer.compare(x,y);

}



Comparator<Inter>  com =(x,y)->{

System.out.pringtln('hello"');

return   Integer.compare(x,y);}



Lambda表达式的参数的数据类型可以不写,因为Java可以对数据类型进行推断

```java
BinaryOperator<Integer> bo = (Integer a, Integer b) -> { return a + b; };
```

![image-20220812194556011](images\image-20220812194556011.png)

