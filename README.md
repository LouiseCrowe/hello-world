# hello-world
First GitHub Repository
public class Methods {
    public static void main(String[] args) {
       sayHello();
       greeting("Louise");
       //add(5, 7);
       multiply(7,3);
       String merged = concat("you are ", "super!");
       System.out.println(merged);
       System.out.println(isEven(45));
        System.out.println(isEven(22));
//        String grade = getGrade(99);
//        System.out.println(grade);
        String grade = getGrade(70);
        System.out.println(grade);
        int higher = compare(59, 11);
        System.out.println(higher);
        String positive = isPositive(7);
        System.out.println(positive);
        int sum = sumUpTo(6);
        System.out.println(sum);
        int factorial = factorial(5);
        System.out.println(factorial);
        printMultiplicationTable(7);
        int[] array = createArrray(7);
        System.out.println(toString(array));
        

    }
//
//    ### Basic Print Method
//    Create a static method sayHello() that prints "Hello, World!". Call the method from the main method.

    public static void sayHello() {
        System.out.println("Hello, world!");
    }
//
//### Parameter Passing
//    Create a static method greet(String name) that prints "Hello, [name]!".
//    Call it with different names.
    public static void greeting(String name) {
        System.out.println("Hello, " + name);
}

//
//### Addition Method
//    Write a static method add(int a, int b) that adds two integers and
//    prints the result. Call it from the main method.
//    public static int add(int a, int b) {
//        int result = a + b;
//        System.out.println(result);
//        return result;
//    }

//
//
//            ### Return a Value
//    Create a static method multiply(int a, int b) that multiplies
//    two numbers and returns the result. Print the returned value.
//
public static int multiply(int a, int b) {
    int result = a * b;
    System.out.println(result);
    return result;
}


//            ### String Concatenation
//    Write a static method combineStrings(String a, String b) that
//    concatenates two strings and returns the result. Print the result in main.
//
public static String concat(String a, String b) {
    String merged = a.concat(b);
    return merged;
}
//
//### Check Even or Odd
//    Create a static method isEven(int number) that returns true
//    if the number is even and false otherwise. Test the method with different numbers.

    public static boolean isEven(int number) {
        return (number % 2 == 0);
    }


//
//            ### Grade Evaluator
//    Write a static method getGrade(int score) that returns:
//
//            "A" for score >= 90
//            "B" for score >= 80
//            "C" for score >= 70
//            "F" for all others.
//    Print the grade for multiple scores in main.

    public  static String getGrade(int mark) {
        if (mark >= 90) {
            return "A";
        } else if (mark >= 80) {
            return "B";
        } else if (mark >= 70) {
            return "C";
        } else {
            return "F";
        }
    }

//
//            ### Compare Two Numbers
//    Create a static method max(int a, int b) that returns the
//    larger of two numbers. Call it with different values.
//
    public static int compare(int a, int b) {
        if (a > b) {
            return a;
        } else return b;
    }
//
//### Positive or Negative
//    Write a static method isPositive(int number) that
//    returns "positive", "negative", or "zero" based on the number. Print the result.
//
    public static String isPositive(int number) {
        if (number == 0) {
            return "zero";
        } else if (number > 0) {
                             return "positive";
        } else {
            return "negative";
        }
    }
//
//### Sum of Numbers
//    Create a static method sumUpTo(int n) that returns the
//    sum of all integers from 1 to n. For example, sumUpTo(5) returns 15.
//
    public static int sumUpTo(int n) {
        int sum = 0;

        for(int i = 1; i <= n; i++) {
            sum += i;
        }
        return sum;
    }
//
//            ### Factorial
//    Write a static method factorial(int n) that calculates the factorial
//    of a number using a loop. For example, factorial(4) returns 24.
//
    public static int factorial(int n) {
        int product = 1;

        for(int i = 1; i <= n; i++) {
            product *= i;
        }
        return product;
    }
//
//            ### Print Multiplication Table
//    Create a static method printMultiplicationTable(int n) that
//    prints the multiplication table of n (up to 10).
//    For example, printMultiplicationTable(3) prints:
//
//
//            - 3 x 1 = 3
//            - 3 x 2 = 6
//            - ...
//            - 3 x 10 = 30
    public static void printMultiplicationTable(int n) {
      for (int i = 1; i <= 10; i++ ){
          System.out.println(n + " x " + i + " = " + (n * i));
      }
    }

//
//
//            ### Return an Array
//    Write a static method createArray(int n) that returns an
//    array of size n, filled with numbers from 1 to n.
//    For example, createArray(5) returns [1, 2, 3, 4, 5].
    public static int[] createArrray(int n) {
        int[] array = new int[n];

        for (int i = 0; i < n; i++) {
            array[i] = i + 1;
        }
        return array;
    }

//
//
//            ### Find Maximum in Array
//    Create a static method findMax(int[] numbers) that returns the largest number in an array. Test it with different arrays.
//
//### Filter Even Numbers
//    Write a static method filterEvens(int[] numbers) that returns a new array containing only the even numbers from the input array. For example, filterEvens([1, 2, 3, 4]) returns [2, 4].




}
