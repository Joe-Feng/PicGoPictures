从键盘获取不同类型的变量

1. 导包：import java.util.Scanner;
2. Scanner的实例化
3. 调用 Scanner 类的方法（next()/ nextXxx()），来获取指定类型的变量

注意：

需要根据相应的方法，输入相类型的数据，否则程序会终止

```java
//导包
import java.util.Scanner;
    
    class ScannerTest{
        public static void main(String[] args){
            //Scanner的实例化
            Scanner scan = new Scanner(System.in);
            
            //调用 Scanner 类的方法
            System.out.println("请输入你的姓名：");
            String name = scan.next();//String使用的函数比较特殊/next()
            System.out.println(name);
            
            System.out.println("请输入你的芳龄：");
            int age = scan.nextInt();
            System.out.println(age);
            
            System.out.println("请输入你的体重：");
            double weight = scan.nextDouble();
            System.out.println(weight);
            
            System.out.println("你是否相中了我(true/false)：");
            boolean isLove = scan.nextBoolean();
            System.out.println(isLove);
        }
    }
```

> 岳小鹏参加Java考试，他和父亲岳不群达成承诺：如果：成绩为100分时，奖励一辆BMW；成绩为(80， 99]时，奖励一台iphone xs max；当成绩为[60,80]时，奖励一个 iPad；其它时，什么奖励也没有。从键盘输入岳小鹏的期末成绩，并加以判断  
>
> ![image-20200910190551205](E:\typora保存图片\image-20200910190551205.png)

```java
import java.util.Scanner;

class IfTest1{
    public static void main(String[] args){
        Scanner scan = new Scanner(System.in);
        System.out.println("请出入岳小鹏的成绩(0~100)：");
        int score = scan.nextInt();
        
        if(score == 100){
            System.out.println("奖励一台BWM");
        }
        else if(score > 80 && score <= 99){
            System.out.println("奖励一台iPhone xs max");
        }
        else if(score >= 60 && score <= 80){
            System.out.println("奖励一台ipad");
        }
        else{
            System.out.println("什么也不奖励");
        }
    }
}
```

> 编写程序：由键盘输入三个整数分别存入变量num1、 num2、 num3，
> 对它们进行排序(使用 if-else if-else),并且从小到大输出。  

总结：

1. if-else可以嵌套
2. 如果if-else 结构中的执行语句只有一行时，对应的一对{}可以省略，但是不建议

```java
import java.util.Scanner;
class Sort{
    public static void main(String[] args){
        Scanner scan = new Scanner(System.in);
        
        System.out.println("请输入第一个数：");
        int num1 = scan.nextInt();
        System.out.println("请输入第二个数：");
        int num2 = scan.nextInt();
        System.out.println("请输入第三个数：");
        int num3 = scan.nextInt();
        
        if(num1 <= num2){
            if(num2 <= num3){
                System.out.println(num1 + "," + num2 + "," + 				 num3);
            }else if(num3 <= num1){
                System.out.println(num3 + "," + num1 + "," + 				 num2);
            }else{
                System.out.println(num1 + "," + num3 + "," + 				 num2);
            }
        }else{
            if(num3 >= num1){
                System.out.println(num3 + "," + num1 + "," + 				 num2);
            }else if(num3 <= num2){
                System.out.println(num1 + "," + num2 + "," + 				 num3);
            }else{
                System.out.println(num1 + "," + num3 + "," + 				 num2);
            }
        }
    }
}
```

> 我家的狗5岁了， 5岁的狗相当于人类多大呢？其实，狗的前两年每
> 一年相当于人类的10.5岁，之后每增加一年就增加四岁。那么5岁的狗
> 相当于人类多少年龄呢？应该是： 10.5 + 10.5 + 4 + 4 + 4 = 33岁。
> 编写一个程序，获取用户输入的狗的年龄，通过程序显示其相当于人
> 类的年龄。如果用户输入负数，请显示一个提示信息。  

```java
improt java.util.Scanner;

class DogAge{
    public static void main(String[] args){
        Scanner scan = new Scanner(System.in);
        
        System.out.println("请输入狗的年龄：");
        int age = scan.nextInt();
        if(age < 0){
            System.out.println("输入的数据非法");
        }else{
            if(age <= 2){
                System.out.println("狗的年龄相当于人的年龄" + age * 10.5);
            }else{
                System.out.println("狗的年龄相当于人的年龄" + 2 * 10.5 + (age - 2) * 4);
            }
        }
    }
}
```

