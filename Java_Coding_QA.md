# Java Programs

## 1. Reverse String in Java Without Using Readymade Functions ?

### Code
```java
class ReverseString {
    public static void main(String[] args) {
        String str = "Hello World";
        System.out.println("Before Reversing String: " + str); // Before Reversing String: Hello World
        String reverseStr = "";
        for(int i = str.length() - 1; i >= 0; i--) {
            reverseStr += str.charAt(i);
        }
        System.out.println("After Reversing String: " + reverseStr); // After Reversing String: dlroW olleH
    }
}
```
## 2. How Do You Swap Two Numbers Without Using a Third Variable in Java ?

### Code
```java
class SwapTwoNo {
    public static void main(String[] args) {
       int no1 = 15;
       int no2 = 34;
       System.out.println("No before swapping: " + no1 + " " + no2); // No before swapping: 15 34
       no1 = no1 + no2;
       no2 = no1 - no2;
       no1 = no1 - no2;
       
       System.out.println("No after swapping: " + no1 + " " + no2); // No after swapping: 34 15
    }
}
```
## 3. Write a Java Program to Check if a Vowel is Present in a String ?

### Code
```java
class CheckVowel {
    public static void main(String[] args) {
        String str = "HellO";
        Boolean isVowel = false;
        String castToLowerCase = str.toLowerCase();
        for (int c = 0; c < castToLowerCase.length(); c++) {
            if (castToLowerCase.charAt(c) == 'a' || castToLowerCase.charAt(c) == 'e' || 
                castToLowerCase.charAt(c) == 'i' || castToLowerCase.charAt(c) == 'o' || 
                castToLowerCase.charAt(c) == 'u') {
                isVowel = true;
                break;
            }
        }
        if (isVowel) {
            System.out.println("Vowel present in string " + str); // Vowel present in string HellO
        } else {
            System.out.println("Vowel not present in string " + str);
        }
    }
}
```
## 4. Write a Java Program to Check if the Given Number is a Prime Number ?

### Code
```java
class CheckPrimeNo {
    public static void main(String[] args) {
        boolean isPrimeNo = true;
        int no = 11;
        
        if (no == 0 || no == 1) {
            isPrimeNo = false;
        } else {
            for (int i = 2; i <= no / 2; i++) {
                if (no % i == 0) {
                    isPrimeNo = false;
                    break; 
                }
            }
        }
        
        if (isPrimeNo) {
            System.out.println("No is prime: " + no); // No is prime: 11
        } else {
            System.out.println("No is not prime: " + no);
        }
    }
}
```
## 5. Write a Java Program to Print a Fibonacci Sequence Using Recursion ?

### Code
```java
class FibonacciSequence {
    public static void printFibonacciSequence(int count) {
        int a = 0;
        int b = 1;
        int c = 1;

        for (int i = 0; i <= count; i++) {
            System.out.print(a + ", "); // 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55,
            a = b;
            b = c;
            c = a + b;
        }
    }

    public static void main(String[] args) {
        printFibonacciSequence(10);
    }
}
```
## 6. How Do You Check if a List of Integers Contains Only Odd Numbers in Java ?

### Code
```java
import java.util.*;
import java.util.stream.Collectors;

class CheckOddNo {
    public static void main(String[] args) {
        ArrayList<Integer> li = new ArrayList<Integer>();
        li.add(1);
        li.add(9);
        li.add(8);
        li.add(2);
        li.add(4);
        System.out.println(li); // [1, 9, 8, 2, 4]
        List<Integer> oddNo = li.stream()
                                .filter(n -> n % 2 != 0)
                                .collect(Collectors.toList());
        if (!oddNo.isEmpty()) {
            System.out.println("Odd No Present"); // Odd No Present
        } else {
            System.out.println("Odd No Not Present");
        }
    }
}
```
## 7. How Do You Check Whether a String is a Palindrome in Java ?

### Code
```java
class StringPalindrome {
    public static void main(String[] args) {
        String str = "madam";
        String rev = "";
        for (int i = str.length() - 1; i >= 0; i--) {
            rev += str.charAt(i);
        }
        if (str.equals(rev)) {
            System.out.println("String is palindrome"); // String is palindrome
        } else {
            System.out.println("String is not palindrome");
        }
    }
}
```
## 8. How Do You Remove Spaces from a String in Java ?

### Code
```java
class RemoveWhiteSpace {
    public static void main(String[] args) {
       String str = "  hello world   ";
       String result = "";
       System.out.println("Before removing space: " + str); // Before removing space:   hello world   
       for (int i = 0; i < str.length(); i++) {
           if (str.charAt(i) != ' ') {
               result += str.charAt(i);
           }
       }
       System.out.println("After removing space: " + result); // After removing space: helloworld
    }
}
```
## 9. How Do You Remove Leading and Trailing Spaces from a String in Java ?

### Code
```java
class LeadingAndTrailingSpace {
    public static void main(String[] args) {
       String str = "  hello world   ";
       str = str.strip();
       System.out.println(str); // Output: hello world
    }
}
```
## 10. How Do You Sort an Array in Java ?

### Code
```java
import java.util.*;

class SortArray {
    public static void main(String[] args) {
        int a[] = {1, 4, 6, 2, 9, 12, 3};
        System.out.println("Before Sort " + Arrays.toString(a)); // Before Sort [1, 4, 6, 2, 9, 12, 3]

        // Bubble Sort Implementation
        for (int i = 0; i < a.length - 1; i++) {
            for (int j = i + 1; j < a.length; j++) {
                if (a[i] > a[j]) {
                    // Swap
                    int temp = a[i];
                    a[i] = a[j];
                    a[j] = temp;
                }
            }
        }

        System.out.println("After sort " + Arrays.toString(a)); // After sort [1, 2, 3, 4, 6, 9, 12]
    }
}
```
