---
title: Access Modifiers
localeTitle: 访问修饰符
---
# 访问修饰符

你有没有想过定义人们如何访问你的一些房产？你不希望任何人使用你的内衣。但是，亲密的朋友和亲戚可以使用你的毛衣，也许你的车。

与您设置访问级别的方式类似，Java也控制访问权限。您希望根据要访问它们的其他类来定义变量，方法和类的访问级别。

Java提供了4级访问修饰符。这意味着您可以通过4种方式修改对变量，方法或类的访问。这4种方式是私有的，公共的，受保护的和默认的。

这些访问修饰符可以应用于字段，方法和类（类是一种特殊情况，我们将在本文末尾查看它们）。以下是每个`Access Modifier`的`Access Levels`的快速概述1 ：

#### 访问修饰符表参考：

![访问修饰符表](https://cdn-media-1.freecodecamp.org/imgr/zoMspyn.png)

#### 私人访问修改器

允许仅在创建变量或方法的类中访问它。除了创建变量或方法的类之外，没有其他类可以访问它。这与您的内脏非常相似。它们仅供业主使用。要将变量或方法设为私有，只需在变量或方法类型之前附加private关键字即可。 让我们在编码示例中使用private。如果一家银行想要为其贷款提供10％的利率，那么它将确保利率变量（让我们假设`int int_rate;` ）保持私有，以便其他类别不会尝试访问并更改它。 例如;

`private String name;`

上面的示例创建了一个名为name的变量，并确保它只能在创建它的类中访问。

方法的另一个例子是 `java private void setAge(){ System.out.println("Set Age"); }` 上面的示例确保方法setAge只能在创建它的类中访问，而不能在其他任何地方访问。

#### 公共访问修饰符

公共访问修饰符与私有访问修饰符直接相反。类，方法或变量可以声明为public，这意味着可以从任何类访问它。公共访问修饰符可以比作公立学校，任何人都可以寻求入学和录取。

可以随时从任何其他类访问公共类，方法或变量。

例如，要将类声明为public，您只需要：

```java
public class Animal{ 
 
 } 
```

因此，Animal类可以被任何其他类访问。

```java
public int age; 
 public int getAge(){ 
 } 
```

以上是将变量和方法指定为公共的方法。

#### 默认访问修饰符

默认访问修饰符与所有其他访问修饰符的不同之处在于它没有关键字。要使用默认访问修饰符，您只需使用其他访问修饰符，这只是意味着您使用的是默认访问修饰符。

例如，要使用类的默认访问修饰符，请使用

```java
class Bird{ 
 } 
```

这基本上意味着您正在使用默认访问修饰符。默认访问修饰符允许同一包中的其他类可以访问变量，方法或类。包是文件目录中相关类的集合。有关包的更多信息，请查看包中的部分。

声明为使用默认访问修饰符的任何变量，方法或类都不能被声明它的包之外的任何其他类访问。

```java
int age; 
 void setNewAge(){ 
 } 
```

以上是对变量或方法使用默认访问修饰符的一些方法。 别忘了，默认访问修饰符没有关键字。缺少其他3个访问修饰符意味着您正在使用默认访问修饰符。

#### 受保护的访问修饰符

受保护的访问修饰符与默认访问修饰符密切相关。受保护的访问修饰符具有默认访问修饰符的属性，但稍有改进。

变量和方法是唯一使用受保护的访问修饰符的方法。稍微改进的是，声明变量或方法的类包之外的类可以访问所述变量或方法。但是，如果它继承自Class，则这是可能的。

来自另一个可以看到受保护变量或方法的包的类必须扩展创建变量或方法的类。

注意，如果没有继承的优点，默认访问修饰符与受保护的访问修饰符具有完全相同的访问权限。

使用受保护的访问修饰符的示例如下所示：

```java
protected int age; 
 protected String getName(){ 
  return "My Name is You"; 
 } 
```

#### 访问类的修饰符

默认情况下，类只能有2个修饰符：

*   上市
*   无修饰符（默认修饰符）

那么这意味着类永远不能设置为`private`或`protected` ？

这是合乎逻辑的，你为什么要私人上课？没有其他类可以使用它。但有时候，你可以将一个类嵌入到另一个类中。这些特殊的类， `inner classes` ，可以设置为private或protected，以便只有它的周围类可以访问它：

```java
public class Car { 
    private String brand; 
    private Engine engine; 
    // ... 
    private class Engine { 
        // ... 
    } 
 } 
```

在上面的示例中，只有`Car`类可以使用`Engine`类。在某些情况下，这可能很有用。

其他类永远不能设置为`protected`或`private` ，因为它没有任何意义。 `protected`访问修饰符用于使`package-private`但具有子类可访问的选项。在java中没有诸如“子包”或“包继承”之类的概念。

### 来源

[1.关于Access Modifiers的Oracle文档](https://docs.oracle.com/javase/tutorial/java/javaOO/accesscontrol.html "Oracle Docs")