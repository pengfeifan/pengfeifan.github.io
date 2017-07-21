---
layout: post
title: note-TIJ4 Thinking in Java
categories:
- notes
---
Java编程思想4
===


# Chapter1.对象导论

## 1.抽象过程 class

## 2.每个对象都有一个接口

- 创建抽象数据类型 **类**
- 接口确定了对某一特定对象所能发出的请求

## 3.每个对象都提供服务

- 高内聚

## 4.被隐藏的具体实现

- 访问控制
>private/ protected /public /default

## 5.复用具体实现

- 组合 has-a

## 6.继承 extends
- 覆盖
- is-a
- is-like-a

## 7.伴随多态的可互换对象

- 后期绑定（动态绑定）
- 向上转型

## 8.单根继承结构

- Object

## 9.容器

- 数组
- 集合
- 参数化类型（泛型）

## 10.对象的创建和生命期

- 堆栈
- 堆
- 垃圾回收器

## 11.异常处理：处理错误

## 12.并发编程

- 多线程
- 共享资源

## 13.Java与Internet

#  Chapter2.一切都是对象

## 1.用引用操纵对象

- 创建一个引用的时候便初始化

## 2.必须由你创建所有对象

- 存储
>寄存器、堆栈、堆、常量存储、非RAM存储（流对象、持久化对象）

- 基本类型
>boolean /char /byte /short /int /long /float /double /void 

- 高精度数字：BigInteger(整数)  BigDecimal(定点数)

## 3.永远不需要销毁对象

- 作用域

## 4.创建新的数据类型：类

- 字段(数据成员)和方法(成员函数)
- 基本成员默认值

## 5.方法、参数和返回值

- 向对象发送消息
- 参数列表

## 6.构建一个Java程序

- 名字可见性：包 package
- 运用其他构件：import
- static关键字：类数据、类方法

## 7.Java helloworld

```java
  package com.github.helloworld

  import java.util.*;

  public class HelloWorld{
      public static void main(String[] args){
          System.out.println("Hello.World");
          System.out.println(new Date());
      }
  }
```

- 编译 `javac` HelloWorld.java
- 运行 `java` HelloWorld

## 8.注释和嵌入式文档

- 文档注释 Javadoc
- @see：引用其他类
- @version
- @author
- @since
- @param
- @return
- @throws
- @deprecated

## 编码风格：驼峰风格

#  Chapter3.操作符

- 算术操作符
- 自动递增递减
- 关系运算符
	*  基本类型` == `     `！=`
	*  引用类型` equals`
- 逻辑运算符
	*  短路 `&&` 		`|| `	`！`
- 直接常量
- 按位操作符
- 移位操作符
	* 无符号右移 >>>
- 三元操作符 `boolean-exp？true-val1：false-val2`
- 字符串操作符 +和 +=
- 类型转换操作符		(type)

#  Chapter4.控制执行流程

- true & false
- if-else
- 迭代
	*  while do-while for
	*  逗号操作符
- Foreach语法
- return
- break & continue
- goto保留字
- switch

#  Chapter5.初始化与清理

## 1.用构造器确保初始化

- 构造器的名字必须与类名完全相同

## 2.方法重载

## 3.默认构造器（无参构造器）

## 4.this关键字

- 调用方法的那个对象
- static方法的内部不能调用非静态方法，static方法不能有this

## 5.清理：终结处理和垃圾回收

- finalize()方法
- 对象可能不被垃圾回收
- 垃圾回收并不等于"析构"
- 垃圾回收只与内存有关
- System.gc()
- Just-In-Time ,JIT 即时编译

## 6.成员初始化

## 7.构造器初始化

- 初始化顺序：变量定义的先后顺序决定了初始化的顺序。
- 静态数据的初始化：先静态对象 然后 ”非静态“对象
- 显示的静态初始化：“静态块”
- 非静态实例初始化

## 8.数组初始化

- 可变参数列表  (type... args)

## 9.枚举类型

- enum

#  Chapter6.访问权限控制

## 1.包：库单元

- public类的名称必须与文件的名称相同
- 代码组织
- 创建独一无二的包名：反序的Internet域名
- 定制工具库：import static
- 用import改变行为

## 2.Java访问权限修饰词

- 包访问权限（默认访问权限）
- public：接口访问权限；
- private：你无法访问
- protected：继承访问权限

## 3.接口和实现

- 封装

## 4.类的访问权限：包访问权限或public

- 每个编译单元（文件）都只能有一个public类
- public类的名称必须完全与含有该编译单元的文件名相匹配，包括大小写。
- 虽然不是很常用，但编译单元内完全不带public类也是可能的，这个类就拥有了包访问权限。

**访问权限控制专注于类创建者和该类库的外部使用者之间的关系，这种关系也是一种通信方式。**

#  Chapter7.复用类

## 1.组合语法

- toString()方法

## 2.继承语法

- 初始化基类
	* 自动执行基类的无参构造器
	* 带参数的构造器 super

## 3.代理

## 4.结合使用组合和继承

- 确保正确清理
	try{保护区}		finally
- 名称屏蔽
	@Override
    
## 5.在组合与继承之间选择

组合技术通常用于想在新类中使用现有类的功能而非它的接口这种情形。即，在新类中嵌入某个对象，让其实现所需要的功能，但新类的用户看到的只是为新类所定义的接口，而非所嵌入对象的接口。为取得此效果，需要在新类中嵌入一个现有类的private对象。

在继承的时候，使用某个现有类，并开发一个它的特殊版本。通常，这意味着你在使用一个通用类，并为了某种特殊需要而将其特殊化。

## 6.protected关键字

- 通过protected方法来控制类的继承者的访问权限

## 7.向上转型

- 继承类是基类的一种类型
- 向上转型是从一个专用类型向较通用类型转换，导出类是基类的一个超集。
- 如果需要使用向上转型就采用继承

## 8.final关键字

### final数据

- final数据
	* 常量：用final修饰基本数据类型。
	* 用final修饰对象（引用类型），无法改为指向另一个对象，但该对象自身是可以修改的。
	* 根据惯例，既是static又是final的域（即编译期常量）将用大写表示，并用下划线分割各个单词。在对编译期常量进行定义的时候，必须对其进行赋值。
- 空白final
	* Java允许生成“空白final”，所谓空白final是指被声明为final但又未给定初值的域。
	* 必须在域的定义处或者每个构造器中用表达式对final进行赋值，这正是final域在使用前总是被初始化的原因所在。
- final参数
	* Java允许在参数列表中以声明的方式将参数指明为final。这意味着你无法再方法中更改参数引用所指向的对象。

### final方法

final方法把方法锁住，以防任何继承类修改它它的含义，并且不会被覆盖。只有在想要明确禁止覆盖时，才将方法设置为final的。
- final和private关键字
- final可以有效的“关闭”动态绑定。

### final类

final类禁止继承，所以final类中所有的方法都隐式指定为final的。

## 9.初始化及类的加载

- 继承与初始化

```java
package com.github.tij4.chap7;

class Insect {
	private int i = 9;
	protected int j;

	Insect() {
		System.out.println("i= " + i + ",j= " + j);
		j = 39;
	}

	private static int x1 = printInit("static Insect.x1 initialized");

	static int printInit(String s) {
		System.out.println(s);
		return 47;
	}
}

public class Beetle extends Insect {

	private int k = printInit("Beetle.k initialized");

	public Beetle() {
		System.out.println("k= " + k);
		System.out.println("j= " + j);
	}

	private static int x2 = printInit("static Beetle.x2 Initialized");

	public static void main(String[] args) {
		System.out.println("Beetle constructor");
		Beetle b = new Beetle();
	}
	/* Output:
		static Insect.x1 initialized
		static Beetle.x2 Initialized
		Beetle constructor
		i= 9,j= 0
		Beetle.k initialized
		k= 47
		j= 39
	 */

}
```

#  Chapter8.多态

多态是继数据抽象和继承以后的第三种基本特征。<br/>
多态通过分离*做什么*和*怎么做*，从另一种角度讲接口和实现分离开来。多态不但能够改善代码的组织结构和可读性，还能够创建*可扩展*的程序。

将一个方法调用同一个方法主体关联起来被称为**绑定**。<br/>
若在程序执行前进行绑定，叫做**前期绑定**。<br/>
**后期绑定**，它的含义就是在运行时根据对象的类型进行绑定。后期绑定也叫做动态绑定、运行时绑定。

- 只有非private方法才可以被覆盖。
- 只有普通的方法调用可以多态的。

## 构造器和多态

- 构造器的调用顺序
	* 1.调用基类构造器
	* 2.按声明顺序调用成员的初始化方法
	* 3.调用导出类构造器的主体
- 继承与清理

```java
package com.github.tij4.chap8;

class Characteristic {
	private String s;

	Characteristic(String s) {
		this.s = s;
		System.out.println("Creating Characteristic " + s);
	}

	protected void dispose() {
		System.out.println("disposing Characteristic " + s);
	}
}

class Description {
	private String s;

	Description(String s) {
		this.s = s;
		System.out.println("Creating Description " + s);
	}

	protected void dispose() {
		System.out.println("disposing Description " + s);
	}
}

class LivingCreature {
	private Characteristic p = new Characteristic("is alive");
	private Description t = new Description("Basic Living Creature");

	LivingCreature() {
		System.out.println("LivingCreature()");
	}

	protected void dispose() {
		System.out.println("LivingCreature dispose");
		t.dispose();
		p.dispose();
	}
}

class Animal extends LivingCreature {
	private Characteristic p = new Characteristic("has heart");
	private Description t = new Description("Animal not Vegetable");

	Animal() {
		System.out.println("Animal()");
	}

	protected void dispose() {
		System.out.println("Animal dispose");
		t.dispose();
		p.dispose();
		super.dispose();
	}
}

class Amphibian extends Animal {
	private Characteristic p = new Characteristic("can live in water");
	private Description t = new Description("Both water and land");

	Amphibian() {
		System.out.println("Amphibian()");
	}

	protected void dispose() {
		System.out.println("Amphibian dispose");
		t.dispose();
		p.dispose();
		super.dispose();
	}

}

public class Frog extends Amphibian {

	private Characteristic p = new Characteristic("Croaks");
	private Description t = new Description("Eats Bugs");

	Frog() {
		System.out.println("Frog()");
	}

	protected void dispose() {
		System.out.println("Frog dispose");
		t.dispose();
		p.dispose();
		super.dispose();
	}

	public static void main(String[] args) {
		Frog frog = new Frog();
		System.out.println("Bye!");
		frog.dispose();
	}
}
/*Output:
Creating Characteristic is alive
Creating Description Basic Living Creature
LivingCreature()
Creating Characteristic has heart
Creating Description Animal not Vegetable
Animal()
Creating Characteristic can live in water
Creating Description Both water and land
Amphibian()
Creating Characteristic Croaks
Creating Description Eats Bugs
Frog()
Bye!
Frog dispose
disposing Description Eats Bugs
disposing Characteristic Croaks
Amphibian dispose
disposing Description Both water and land
disposing Characteristic can live in water
Animal dispose
disposing Description Animal not Vegetable
disposing Characteristic has heart
LivingCreature dispose
disposing Description Basic Living Creature
disposing Characteristic is alive

 */


```

- 构造器内部的多态方法的行为

```java
package com.github.tij4.chap8;

class Glyph {
	void draw() {
		System.out.println("Glyph.draw()");
	}

	Glyph() {
		System.out.println("Glyph() before draw()");
		draw(); // polymorphism
		System.out.println("Glyph() after draw()");
	}
}

class RoundGlyph extends Glyph {
	private int radius = 1;

	RoundGlyph(int r) {
		radius = r;
		System.out.println("RoundGlyph.RoundGlyph.radius= " + radius);
	}

	void draw() {
		System.out.println("RoundGlyph.draw().radius= " + radius);
	}
}

public class PolyConstructors {

	public static void main(String[] args) {
		new RoundGlyph(7);
	}
}

/*Output:
Glyph() before draw()
RoundGlyph.draw().radius= 0
Glyph() after draw()
RoundGlyph.RoundGlyph.radius= 7 
 */
```

## 协变返回类型

- 表示在导出类中的被覆盖方法可以返回基类方法的返回类型的某种导出类型。

```java
package com.github.tij4.chap8;

class Grain {
	public String toString() {
		return "Grain";
	}
}

class Wheat extends Grain {
	public String toString() {
		return "Wheet";
	}
}

class Mill {
	Grain process() {
		return new Grain();
	}
}

class WheatMill extends Mill {
	Wheat process() {
		return new Wheat();
	}
}

public class CovariantReturn {

	public static void main(String[] args) {
		Mill m = new Mill();
		Grain g = m.process();
		System.out.println(g);
		m = new WheatMill();
		g = m.process();
		System.out.println(g);
	}
}
/*Output:
Grain
Wheet
*/
```

## 用继承进行设计

- 用继承表达行为间的差异，并用字段表达状态上的变化
- 纯继承与扩展 **is-a**
- `向下转型`与`运行时类别识别（RTTI）`

#  Chapter9.接口

**接口和内部类为我们提供了一种将接口和实现分离的更加结构化的方法**

## 1.抽象类(抽象基类)和抽象方法：abstract

- 抽象方法：没有方法体，`abstract void f();`
- 包含抽象方法的类叫做抽象类，**abstract**

## 2.接口：interface

- 接口被用用来建立类与类之间的协议。
- 接口支持多重继承
- 接口可以包含域，不过这些域隐式的是*static*和*fianl*
- 实现接口：implements

## 3.完全解耦

- 将接口从具体实现中解耦使得接口可以应用于多种不同的具体实现，因此代码也就更具可复用性。

```java
package com.github.tij4.chap9.interfaceprocessor;

public interface Processor {

	String name();

	Object process(Object input);

}
```

```java
package com.github.tij4.chap9.interfaceprocessor;

public class Apply {

	public static void process(Processor p, Object s) {
		System.out.println("Using Processor " + p.name());
		System.out.println(p.process(s));
	}
}
```

```java
package com.github.tij4.chap9.interfaceprocessor;

import java.util.Arrays;

class Upcase extends StringProcessor {
	public String process(Object input) {
		return ((String) input).toUpperCase();
	}
}

class Downcase extends StringProcessor {
	public String process(Object input) {
		return ((String) input).toLowerCase();
	}
}

class Splitter extends StringProcessor {
	public String process(Object input) {
		return Arrays.toString(((String) input).split(" "));
	}
}

public abstract class StringProcessor implements Processor {

	public String name() {
		return getClass().getSimpleName();
	}

	public abstract String process(Object input);

	public static String s = "If she weighs the same as a duck. she's made of wood";

	public static void main(String[] args) {
		Apply.process(new Upcase(), s);
		Apply.process(new Downcase(), s);
		Apply.process(new Splitter(), s);
	}

}
/*
 * Output: 
Using Processor Upcase
IF SHE WEIGHS THE SAME AS A DUCK. SHE'S MADE OF WOOD
Using Processor Downcase
if she weighs the same as a duck. she's made of wood
Using Processor Splitter
[If, she, weighs, the, same, as, a, duck., she's, made, of, wood]
 * 
 */
```

```java
package com.github.tij4.chap9.interfaceprocessor;

import com.github.tij4.chap9.filters.*;

//适配器设计模式

class FilterAdapter implements Processor {
	Filter filter;

	public FilterAdapter(Filter filter) {
		this.filter = filter;
	}

	@Override
	public String name() {
		return filter.name();
	}

	@Override
	public Object process(Object input) {
		return filter.process((Waveform) input);
	}

}

public class FilterProcessor {

	public static void main(String[] args) {
		Waveform w = new Waveform();
		Apply.process(new FilterAdapter(new LowPass(1.0)), w);
		Apply.process(new FilterAdapter(new HighPass(2.0)), w);
		Apply.process(new FilterAdapter(new BandPass(3.0, 4.0)), w);
	}
}
/*Output:
Using Processor LowPass
Waveform 0
Using Processor HighPass
Waveform 0
Using Processor BandPass
Waveform 0
 */
```

## 4.Java中的多重继承

- 组合多个类的接口的行为被称作多重继承。

```java
package com.github.tij4.chap9;

// Multiple
interface CanFight {
	void fight();
}

interface CanSwim {
	void swim();
}

interface CanFly {
	void fly();
}

class ActionCharacter {
	public void fight() {
		System.out.println("ActionCharacter.fight()");
	}
}

class Hero extends ActionCharacter implements CanFight, CanSwim, CanFly {

	@Override
	public void fly() {
		System.out.println("Hero.fly()");
	}

	@Override
	public void swim() {
		System.out.println("Hero.swim()");
	}

}

public class Adventure {

	public static void t(CanFight x) {
		x.fight();
	}

	public static void u(CanSwim x) {
		x.swim();
	}

	public static void v(CanFly x) {
		x.fly();
	}

	public static void w(ActionCharacter x) {
		x.fight();
	}

	public static void main(String[] args) {
		Hero h = new Hero();
		t(h);
		u(h);
		v(h);
		w(h);
	}

}
/*Output:
ActionCharacter.fight()
Hero.swim()
Hero.fly()
ActionCharacter.fight()
 */

```

## 5.通过继承来扩展接口

- interface1 extends interface2,interface3
- 组合接口时的名字冲突；注意返回值类型

## 6.适配接口

- 接口的一种常见用法就是策略设计模式

```java
package com.github.tij4.chap9;

import java.util.Random;

public class RandomDoubles {

	private static Random rand = new Random(47);

	public double next() {
		return rand.nextDouble();
	}

	public static void main(String[] args) {
		RandomDoubles rd = new RandomDoubles();
		for (int i = 0; i < 7; i++) {
			System.out.println(rd.next());
		}
	}
}
/*Output:
0.7271157860730044
0.5309454508634242
0.16020656493302599
0.18847866977771732
0.5166020801268457
0.2678662084200585
0.2613610344283964
 */
 ```
 
 ```java
 package com.github.tij4.chap9;

import java.io.IOException;
import java.nio.CharBuffer;
import java.util.Scanner;

public class AdapterRandomDoubles extends RandomDoubles implements Readable {

	private int count;

	public AdapterRandomDoubles(int count) {
		this.count = count;
	}

	@Override
	public int read(CharBuffer cb) throws IOException {
		if (count-- == 0) {
			return -1;
		}
		String result = Double.toString(next()) + " ";
		cb.append(result);
		return result.length();
	}

	public static void main(String[] args) {
		Scanner s = new Scanner(new AdapterRandomDoubles(7));
		while (s.hasNextDouble()) {
			System.out.println(s.nextDouble() + " ");
		}
	}

}
/*Output:
0.7271157860730044 
0.5309454508634242 
0.16020656493302599 
0.18847866977771732 
0.5166020801268457 
0.2678662084200585 
0.2613610344283964
 */
 ```
 
 **可以在任何现有类之上添加新的接口，所以这意味着让方法接受接口类型，是一种让任何类都可以对该方法进行适配的方式。这就是使用接口而不是类的强大之处。**
 
 ## 7.接口中的域
 
 接口中的任何域都自动是`public`，`static`和`final`的，所以`接口`就成为了一种很便捷的用来创建常量组的工具。现在可以使用更加强大灵活的`enum`关键字。
 
 ## 8.嵌套接口
 
 **接口可以嵌套在类或其他接口中**
 
 ## 9.接口与工厂
 
 **工厂方法设计模式**
 
 在工厂对象上调用的是创建方法，而该工厂对象将生成接口的某个实现的对象。理论上通过这种方式，我们的代码将完全与接口的实现分离，这就使得我们可以透明地将某个实现替换为另一个实现。
 
 ```java
 package com.github.tij4.chap9;

// 工厂方法设计模式
interface Service {
	void method1();

	void method2();
}

interface ServiceFactory {
	Service getService();
}

class Implementation1 implements Service {

	Implementation1() {
	}

	@Override
	public void method1() {
		System.out.println("Implementation1 method1");
	}

	@Override
	public void method2() {
		System.out.println("Implementation1 method2");
	}

}

class Implementation1Factory implements ServiceFactory {

	@Override
	public Service getService() {
		return new Implementation1();
	}

}

class Implementation2 implements Service {

	Implementation2() {
	}

	@Override
	public void method1() {
		System.out.println("Implementation2 method1");
	}

	@Override
	public void method2() {
		System.out.println("Implementation2 method2");
	}

}

class Implementation2Factory implements ServiceFactory {

	@Override
	public Service getService() {
		return new Implementation2();
	}

}

public class Factories {

	public static void serviceConsumer(ServiceFactory factory) {
		Service srvc = factory.getService();
		srvc.method1();
		srvc.method2();
	}

	public static void main(String[] args) {
		serviceConsumer(new Implementation1Factory());
		serviceConsumer(new Implementation2Factory());
	}

}
/*Output:
Implementation1 method1
Implementation1 method2
Implementation2 method1
Implementation2 method2
 */
```
 
 #  Chapter10.内部类

可以将一个`类的定义`放在另一个`类的定义内部`，这就是`内部类`。

 ## 1.创建内部类
 
 ```java
 package com.github.tij4.chap10;

public class Parcel2 {

	class Contents {
		private int i = 11;

		public int value() {
			return i;
		}
	}

	class Destination {
		private String label;

		Destination(String whereTo) {
			label = whereTo;
		}

		String readLabel() {
			return label;
		}
	}

	public Destination to(String s) {
		return new Destination(s);
	}

	public Contents contents() {
		return new Contents();
	}

	public void ship(String dest) {
		Contents c = contents();
		Destination d = to(dest);
		System.out.println(d.readLabel());
	}

	public static void main(String[] args) {
		Parcel2 p = new Parcel2();
		p.ship("Tasmania");

		Parcel2 q = new Parcel2();
		Parcel2.Contents c = q.contents();
		Parcel2.Destination d = q.to("Borneo");
		System.out.println(d.readLabel());
	}

}
/*Output:
Tasmania
Borneo
 */
```

*OuterClassName.InnerClassName*

## 2.连接到外部类

**内部类还拥有其外围类的所有元素的访问权**

```java
package com.github.tij4.chap10;

interface Selector {
	boolean end();

	Object current();

	void next();
}

public class Sequence {

	private Object[] items;
	private int next = 0;

	public Sequence(int size) {
		items = new Object[size];
	}

	public void add(Object x) {
		if (next < items.length) {
			items[next++] = x;
		}
	}

	private class SequenceSelector implements Selector {
		private int i = 0;

		@Override
		public boolean end() {
			return i == items.length;
		}

		@Override
		public Object current() {
			return items[i];
		}

		@Override
		public void next() {
			if (i < items.length) {
				i++;
			}
		}
	}

	public Selector selector() {
		return new SequenceSelector();
	}

	public static void main(String[] args) {
		Sequence sequence = new Sequence(10);
		for (int i = 0; i < 10; i++) {
			sequence.add(Integer.toString(i));
		}

		Selector selector = sequence.selector();
		while (!selector.end()) {
			System.out.print(selector.current() + " ");
			selector.next();
		}
	}

}
/*Output:
0 1 2 3 4 5 6 7 8 9 
*/
```

## 3.使用.this与.new

```java
package com.github.tij4.chap10;

public class DotThis {

	void f() {
		System.out.println("DotThis.f() " + getClass().getSimpleName());
	}

	public class Inner {
		public DotThis outer() {
			return DotThis.this;
		}
	}

	public Inner inner() {
		return new Inner();
	}

	public static void main(String[] args) {
		DotThis dt = new DotThis();
		DotThis.Inner dti = dt.inner();
		dti.outer().f();
	}

}
/*Output:
DotThis.f() DotThis
*/
```

```java
package com.github.tij4.chap10;

public class DotNew {

	public class Inner {
		public void f() {
			System.out.println("Inner.f() " + getClass().getSimpleName());
		}
	}

	public static void main(String[] args) {
		DotNew dn = new DotNew();
		DotNew.Inner dni = dn.new Inner();
		dni.f();
	}
}
/*
Inner.f() Inner
 */
```

## 4.内部类与向上转型

## 5.在方法和作用域内的内部类

- 局部内部类：在方法的作用域内（而不是在其他类的作用域内）创建一个完整的类。

```java
package com.github.tij4.chap10.innerclasses;

public class Parcel5 {

	public Destination destination(String s) {
		class PDestination implements Destination {
			private String label;

			private PDestination(String whereTo) {
				label = whereTo;
			}

			public String readLabel() {
				return label;
			}
		}
		return new PDestination(s);
	}

	public static void main(String[] args) {
		Parcel5 p = new Parcel5();
		Destination d = p.destination("ShangHai");
		System.out.println(d.readLabel());
	}
}
/*
ShangHai
 */
```

## 6.匿名内部类

```java
package com.github.tij4.chap10.innerclasses;

public class Parcel9 {

	public Destination destination(final String dest) {
		return new Destination() {
			private String label = dest;

			public String readLabel() {
				return label;
			}
		};
	}

	public static void main(String[] args) {
		Parcel9 p = new Parcel9();
		Destination d = p.destination("Hangzhou");
		System.out.println(d.readLabel());
	}

}
/*
Hangzhou
*/
```

## 7.嵌套类

- static的内部类

```java
package com.github.tij4.chap10.innerclasses;

public class Parcel11 {

	private static class ParcelContents implements Contents {
		private int i = 11;

		public int value() {
			return i;
		}
	}

	protected static class ParcelDestination implements Destination {
		private String label;

		private ParcelDestination(String whereTo) {
			label = whereTo;
		}

		public String readLabel() {
			return label;
		}

		public static void f() {
		}

		static int x = 10;

		static class AnotherLevel {
			public static void f() {
			}

			static int x = 10;
		}
	}

	public static Destination destination(String s) {
		return new ParcelDestination(s);
	}

	public static Contents contents() {
		return new ParcelContents();
	}

	public static void main(String[] args) {
		Contents c = contents();
		System.out.println(c.value());
		Destination d = destination("china");
		System.out.println(d.readLabel());
	}
}
```

- 接口内部的类

```java
package com.github.tij4.chap10.innerclasses;

public interface ClassInInterface {

	void howdy();

	class Test implements ClassInInterface {
		public void howdy() {
			System.out.println("Howdy!");
		}

		public static void main(String[] args) {
			new Test().howdy();
		}
	}

}
```

- 从多层嵌套类中访问外部类的成员

```java
package com.github.tij4.chap10.innerclasses;

class MNA {
	private void f() {
		System.out.println("MNA.f()");
	}

	class A {
		private void g() {
			System.out.println("MNA.A.g()");
		}

		public class B {
			void h() {
				g();
				f();
			}
		}
	}
}

public class MultiNestingAccess {

	public static void main(String[] args) {
		MNA mna = new MNA();
		MNA.A mnaa = mna.new A();
		MNA.A.B mnaab = mnaa.new B();
		mnaab.h();
	}
}
/*
MNA.A.g()
MNA.f()
 */
```

## 8.为什么需要内部类

**每个内部类都能独立地继承自一个（接口的）实现，所以无论外围类是否已经继承了某个（接口的）实现，对于内部类都没有影响。**

- 闭包与回调，闭包（closure），回调（callback）

```java
package com.github.tij4.chap10.innerclasses;

interface Incrementable {
	void increment();
}

class Callee1 implements Incrementable {
	private int i = 0;

	@Override
	public void increment() {
		i++;
		System.out.println("Callee1.increment:" + i);
	}
}

class MyIncrement {
	public void increment() {
		System.out.println("MyIncrement.increment=====Other operation");
	}

	static void f(MyIncrement mi) {
		mi.increment();
	}
}

class Callee2 extends MyIncrement {
	private int i = 0;

	public void increment() {
		super.increment();
		i++;
		System.out.println("Callee2.increment:" + i);
	}

	private class Closure implements Incrementable {

		@Override
		public void increment() {
			Callee2.this.increment();
		}

	}

	Incrementable getCallbackReference() {
		return new Closure();
	}
}

class Caller {
	private Incrementable callbackReference;

	Caller(Incrementable cbh) {
		callbackReference = cbh;
	}

	void go() {
		callbackReference.increment();
	}
}

public class Callbacks {

	public static void main(String[] args) {
		Callee1 c1 = new Callee1();
		Callee2 c2 = new Callee2();
		MyIncrement.f(c2);
		Caller caller1 = new Caller(c1);
		Caller caller2 = new Caller(c2.getCallbackReference());

		caller1.go();
		caller1.go();
		caller2.go();
		caller2.go();
	}

}
/*Output:
MyIncrement.increment=====Other operation
Callee2.increment:1

Callee1.increment:1

Callee1.increment:2

MyIncrement.increment=====Other operation
Callee2.increment:2

MyIncrement.increment=====Other operation
Callee2.increment:3
 */
```

- 内部类与控制框架

**使变化的事物与不变的事物相互分离**

## 9.内部类的继承

```java
package com.github.tij4.chap10.innerclasses;

class WithInner {
	class Inner {
	}
}

public class InheritInner extends WithInner.Inner {

	InheritInner(WithInner wi) {
		wi.super();
	}

//	public InheritInner(){
//		(new WithInner()).super();
//	}
	
	public static void main(String[] args) {
		WithInner wi = new WithInner();
		InheritInner ii = new InheritInner(wi);
//		InheritInner ii = new InheritInner();
		ii.show();
	}

	public void show() {
		System.out.println("InheritInner.show()");
	}

}
```

## 10.内部类覆盖

```java
package com.github.tij4.chap10.innerclasses;

class Egg2 {
	protected class Yolk {
		public Yolk() {
			System.out.println("Egg2.Yolk()");
		}

		public void f() {
			System.out.println("Egg2.Yolk.f()");
		}
	}

	private Yolk y = new Yolk();

	public Egg2() {
		System.out.println("new Egg2()");
	}

	public void insertYolk(Yolk yy) {
		y = yy;
	}

	public void g() {
		y.f();
	}
}

public class BigEgg2 extends Egg2 {

	public class Yolk extends Egg2.Yolk {
		public Yolk() {
			System.out.println("BigEgg2.Yolk()");
		}

		public void f() {
			System.out.println("BigEgg2.Yolk.f()");
		}
	}

	public BigEgg2() {
		insertYolk(new Yolk());
	}

	public static void main(String[] args) {
		Egg2 e2 = new BigEgg2();
		e2.g();
	}
}
/*
Egg2.Yolk()
new Egg2()
Egg2.Yolk()
BigEgg2.Yolk()
BigEgg2.Yolk.f()
 一个Java类对象在初始化的时候必定是按照一定顺序初始化其 静态块、静态属性、类内部属性、构造方法。
*/
```

## 11.局部内部类

```java
package com.github.tij4.chap10.innerclasses;

interface Counter {
	int next();
}

public class LocalInnerClass {

	private int count = 0;

	// 局部内部类
	Counter getCounter(final String name) {
		class LocalCounter implements Counter {
			public LocalCounter() {
				System.out.println("LocalCounter()");
			}

			public int next() {
				System.out.println(name);
				return count++;
			}
		}
		return new LocalCounter();
	}

	// 匿名内部类
	Counter getCounter2(final String name) {

		return new Counter() {
			{
				System.out.println("Counter()");
			}

			public int next() {
				System.out.println(name);
				return count++;
			}
		};
	}

	public static void main(String[] args) {
		LocalInnerClass lic = new LocalInnerClass();
		Counter c1 = lic.getCounter("Local inner"), c2 = lic.getCounter2("Anonymous inner");
		for (int i = 0; i < 5; i++) {
			System.out.println(c1.next());
		}
		for (int i = 0; i < 5; i++) {
			System.out.println(c2.next());
		}
	}

}
/*Output:
LocalCounter()
Counter()
Local inner
0
Local inner
1
Local inner
2
Local inner
3
Local inner
4
Anonymous inner
5
Anonymous inner
6
Anonymous inner
7
Anonymous inner
8
Anonymous inner
9
 */
```

## 12.内部类标识符

`$`

  #  Chapter11.持有对象
  
  ## 泛型和类型安全的容器
  
  Map:HashMap、TreeMap、LinkedHashMap
  
  ## 迭代器 Iterator ListIterator
  
  ## LinkedList  Stack
  
  ## Set
  
  ## Map
  
  ## Queue
  
  ## PriorityQueue
  
  ## Foreach与迭代器
  
#  Chapter12.通过异常处理错误
  
#  Chapter13.






















