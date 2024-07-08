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
## 11. How Do You Merge Two Lists in Java ?

### Code
```java
import java.util.*;

class MergeTwoList {
    public static void main(String[] args) {
        LinkedList<Integer> l1 = new LinkedList<Integer>();
        LinkedList<Integer> l2 = new LinkedList<Integer>();

        // Adding elements to the first list
        l1.add(1);
        l1.add(2);
        l1.add(3);
        l1.add(4);
        l1.add(5);
        System.out.println("List One: " + l1); // List One: [1, 2, 3, 4, 5]

        // Adding elements to the second list
        l2.add(10);
        l2.add(12);
        l2.add(13);
        l2.add(14);
        l2.add(15);
        System.out.println("List Two: " + l2); // List Two: [10, 12, 13, 14, 15]

        // Merging lists using addAll()
        l1.addAll(l2);
        System.out.println("Merged List: " + l1); // Merged List: [1, 2, 3, 4, 5, 10, 12, 13, 14, 15]
    }
}
```
## 12) How Do You Find the First and Second Largest Number in an Array in Java ?

### Code
```java
import java.util.*;

class FirstAndSecondLargestNo {
    public static void main(String[] args) {
        int a[] = {1, 2, 3, 16, 4, 5, 4, 19, 1, 2, 4, 1};
        System.out.println("Original Array: " + Arrays.toString(a));

        // Using HashSet to remove duplicates
        HashSet<Integer> hs = new HashSet<>();
        for (int i = 0; i < a.length; i++) {
            hs.add(a[i]);
        }
        System.out.println("After Removing Duplicates From Array: " + hs);

        // Converting HashSet to array
        Integer[] sortedArray = hs.toArray(new Integer[0]);
        Arrays.sort(sortedArray);
        System.out.println("Sorted Array: " + Arrays.toString(sortedArray));

        // Finding first and second largest numbers
        System.out.println("First Largest: " + sortedArray[sortedArray.length - 1]);
        System.out.println("Second Largest: " + sortedArray[sortedArray.length - 2]);
    }
}
```
## 13) How Do You Get the Sum of All Elements in an Integer Array in Java?

### Code
```java
import java.util.*;

class SumOfArrays {
    public static void main(String[] args) {
        int a[] = {1, 2, 3, 4, 5};
        int sum = 0;
        System.out.println("Array Before Sum: " + Arrays.toString(a));

        // Calculating sum of array elements
        for (int i = 0; i < a.length; i++) {
            sum += a[i];
        }

        System.out.println("Total Sum: " + sum); // Total Sum: 15
    }
}
```
## 14) Reverse a LinkedList in Java ?

### Code
```java
import java.util.*;

class ReverseLinkedList {
    public static void main(String[] args) {
        LinkedList<Integer> ls = new LinkedList<Integer>();
        LinkedList<Integer> revList = new LinkedList<>();

        // Adding elements to the original list
        ls.add(10);
        ls.add(20);
        ls.add(30);
        ls.add(40);
        ls.add(50);
        System.out.println("Original List: " + ls); // Original List: [10, 20, 30, 40, 50]

        // Reversing the list
        for (int i = ls.size() - 1; i >= 0; i--) {
            revList.add(ls.get(i));
        }
        System.out.println("Reversed List: " + revList); // Reversed List: [50, 40, 30, 20, 10]
    }
}
```
## 15) Write a Program to Find the First Non-Repeating Character in a String in Java?

### Code
```java
import java.util.*;

class FirstNonRepeatingChar {
    public static void main(String[] args) {
        String str = "hello";
        char c = '\0';

        // Finding the first non-repeating character
        for (int i = 0; i < str.length(); i++) {
            boolean isRepeating = false;
            for (int j = 0; j < str.length(); j++) {
                if (i != j && str.charAt(i) == str.charAt(j)) {
                    isRepeating = true;
                    break;
                }
            }
            if (!isRepeating) {
                c = str.charAt(i);
                break;
            }
        }

        // Printing the result
        if (c != '\0') {
            System.out.println("First non-repeating character: " + c); // First non-repeating character: h
        } else {
            System.out.println("No non-repeating character found."); // No non-repeating character found.
        }
    }
}
```
## 16) How Do You Merge Two LinkedLists in Java?

### Code
```java
import java.util.*;

class MergeLinkedList {
    public static void main(String[] args) {
        LinkedList<Integer> l1 = new LinkedList<>();
        LinkedList<Integer> l2 = new LinkedList<>();

        // Adding elements to the first list
        l1.add(1);
        l1.add(2);
        l1.add(3);
        l1.add(4);

        // Adding elements to the second list
        l2.add(11);
        l2.add(12);
        l2.add(13);
        l2.add(14);

        System.out.println("List One: " + l1); // List One: [1, 2, 3, 4]
        System.out.println("List Two: " + l2); // List Two: [11, 12, 13, 14]

        // One Way
        // l1.addAll(l2);
        // System.out.println("After Merging: " + l1); // After Merging: [1, 2, 3, 4, 11, 12, 13, 14]

        // Second Way: Manually adding elements from l2 to l1
        for (int i = 0; i < l2.size(); i++) {
            l1.add(l2.get(i));
        }

        System.out.println("After Merging: " + l1); // After Merging: [1, 2, 3, 4, 11, 12, 13, 14]
    }
}
```
## 17) How Do You Reverse the Order of Words in a String in Java ?

### Code
```java
class ReverseString {
    public static void main(String[] args) {
        String str = "i love programming language very much";
        String result = "";

        // Split the string into words
        String[] words = str.split(" ");
        System.out.println("Before Reverse: " + str); // Before Reverse: i love programming language very much

        // Reverse the order of words
        for (int i = words.length - 1; i >= 0; i--) {
            result += words[i] + " ";
        }

        System.out.println("After Reverse: " + result.trim()); // After Reverse: much very language programming love i
    }
}
```
