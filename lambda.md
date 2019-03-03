# Lambda Expressions

Lambda expressions are introduced in Java 8 and are touted to be the biggest feature of Java 8. Lambda expression facilitates functional programming, and simplifies the development a lot.

## Syntax
A lambda expression is characterized by the following syntax.
```java
(parameters) -> expression
or
(parameters) ->{ statements; }
```
Following are the important characteristics of a lambda expression.
- Optional type declaration − No need to declare the type of a parameter. The compiler can inference the same from the value of the parameter.
- Optional parenthesis around parameter − No need to declare a single parameter in parenthesis. For multiple parameters, parentheses are required.
- Optional curly braces − No need to use curly braces in expression body if the body contains a single statement.
- Optional return keyword − The compiler automatically returns the value if the body has a single expression to return the value. Curly braces are required to indicate that expression returns a value.

## Lambda Expressions Example
```java
public class Java8Tester {

   public static void main(String args[]) {
      Java8Tester tester = new Java8Tester();
		
      //with type declaration
      MathOperation addition = (int a, int b) -> a + b;
		
      //with out type declaration
      MathOperation subtraction = (a, b) -> a - b;
		
      //with return statement along with curly braces
      MathOperation multiplication = (int a, int b) -> { return a * b; };
		
      //without return statement and without curly braces
      MathOperation division = (int a, int b) -> a / b;
		
      System.out.println("10 + 5 = " + tester.operate(10, 5, addition));
      System.out.println("10 - 5 = " + tester.operate(10, 5, subtraction));
      System.out.println("10 x 5 = " + tester.operate(10, 5, multiplication));
      System.out.println("10 / 5 = " + tester.operate(10, 5, division));
		
      //without parenthesis
      GreetingService greetService1 = message ->
      System.out.println("Hello " + message);
		
      //with parenthesis
      GreetingService greetService2 = (message) ->
      System.out.println("Hello " + message);
		
      greetService1.sayMessage("Mahesh");
      greetService2.sayMessage("Suresh");
   }
	
   interface MathOperation {
      int operation(int a, int b);
   }
	
   interface GreetingService {
      void sayMessage(String message);
   }
	
   private int operate(int a, int b, MathOperation mathOperation) {
      return mathOperation.operation(a, b);
   }
}
```


Following are the important points to be considered in the above example.

- Lambda expressions are used primarily to define inline implementation of a functional interface, i.e., an interface with a single method only. In the above example, we've used various types of lambda expressions to define the operation method of MathOperation interface. Then we have defined the implementation of sayMessage of GreetingService.
- Lambda expression eliminates the need of anonymous class and gives a very simple yet powerful functional programming capability to Java.

```java
import java.util.Collections;
import java.util.List;
import java.util.ArrayList;
import java.util.Comparator;
 
public class Java8Tester {
   public static void main(String args[]){
   
      List<String> names1 = new ArrayList<String>();
      names1.add("Google ");
      names1.add("Runoob ");
      names1.add("Taobao ");
      names1.add("Baidu ");
      names1.add("Sina ");
        
      List<String> names2 = new ArrayList<String>();
      names2.add("Google ");
      names2.add("Runoob ");
      names2.add("Taobao ");
      names2.add("Baidu ");
      names2.add("Sina ");
        
      Java8Tester tester = new Java8Tester();
      System.out.println("Java 7 : ");
        
      tester.sortUsingJava7(names1);
      System.out.println(names1);
      System.out.println("Java 8 : ");
        
      tester.sortUsingJava8(names2);
      System.out.println(names2);
   }
   
   //  java 7 sort
   private void sortUsingJava7(List<String> names){   
      Collections.sort(names, new Comparator<String>() {
         @Override
         public int compare(String s1, String s2) {
            return s1.compareTo(s2);
         }
      });
   }
   
   //  java 8 sort
   private void sortUsingJava8(List<String> names){
      Collections.sort(names, (s1, s2) -> s1.compareTo(s2));
   }
}
```

## Loop print out
```java
import java.util.*;
public class LoopDemo {
   public static void main(String args[]){
       // Before Java 8：
        List features = Arrays.asList("Lambdas", "Default Method", "Stream API", "Date and Time API");
        for (String feature : features) {
            System.out.println(feature);
        }

        // After Java 8(using lambda)：
        List features = Arrays.asList("Lambdas", "Default Method", "Stream API", "Date and Time API");
        features.forEach(element -> System.out.println(element));

        // or using method reference
        features.forEach(System.out::println);
   }
}

```

## Filter
Using filter to filter those elements which fit our requirements. For example, we need get the cost which is higher than 25.
```java
import java.util.*;
public class FilterDemo {
   public static void main(String args[]){
        List<Double> cost = Arrays.asList(10.0, 20.0,30.0,40.0);
        List<Double> filteredCost = cost.stream().filter(x -> x > 25.0).collect(Collectors.toList());
        filteredCost.forEach(x -> System.out.println(x));

   }
}
```


## Predicate
```java 

import java.util.*;
public class PredicateDemo {
    public static void main(String[] args) {
        List<String> languages = Arrays.asList("Java","Python","scala","Shell","R");
        System.out.println("Language starts with J: ");
        filterTest(languages,x -> x.startsWith("J"));
        System.out.println("\nLanguage ends with a: ");
        filterTest(languages,x -> x.endsWith("a"));
        System.out.println("\nAll languages: ");
        filterTest(languages,x -> true);
        System.out.println("\nNo languages: ");
        filterTest(languages,x -> false);
        System.out.println("\nLanguage length bigger three: ");
        filterTest(languages,x -> x.length() > 4);
    }
    public static void filterTest(List<String> languages, Predicate<String> condition) {
        languages.stream().filter(x -> condition.test(x)).forEach(x -> System.out.println(x + " "));
    }
}
```

## Map & Map-Reduce
```java
import java.util.*;
public class MapDemo {
   public static void main(String args[]){
        List<Double> cost = Arrays.asList(10.0, 20.0,30.0);
        cost.stream().map(x -> x + x*0.05).forEach(x -> System.out.println(x));//Map
        double allCost = cost.stream().map(x -> x+x*0.05).reduce((sum,x) -> sum + x).get();// Map-reduce
        System.out.println(allCost);
        
        // Traditional way:
        double sum = 0;
        for(double each:cost) {
            each += each * 0.05;
            sum += each;
        }
        System.out.println(sum);
   }
}
```




## Reference:
https://www.tutorialspoint.com/java8/java8_lambda_expressions.htm
https://blog.csdn.net/majishushu/article/details/81123633
