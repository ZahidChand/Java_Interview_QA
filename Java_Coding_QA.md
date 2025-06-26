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
## 18) How Do You Find the Middle Element in a LinkedList in Java?

### Code
```java
import java.util.*;

class MiddleElementLinkedList {
    public static void main(String[] args) {
        LinkedList<Integer> l1 = new LinkedList<Integer>();
        l1.add(10);
        l1.add(20);
        l1.add(30);
        l1.add(40);
        l1.add(50);
        l1.add(60);
        l1.add(70);
        System.out.println("List: " + l1); // List: [10, 20, 30, 40, 50, 60, 70]
        
        int middleIndex = l1.size() / 2;
        System.out.println("Middle element: " + l1.get(middleIndex)); // Middle element: 40
    }
}
```
## 19) How Do You Find the Maximum Element in an Array in Java?

### Code
```java
import java.util.*;

class MaximumElement {
    public static void main(String[] args) {
        int a[] = {12, 34, 90, 13, 45, 67};
        System.out.println("List of elements: " + Arrays.toString(a)); // List of elements: [12, 34, 90, 13, 45, 67]
        
        int max = a[0];
        for (int i = 0; i < a.length; i++) {
            if (a[i] > max) {
                max = a[i];
            }
        }
        System.out.println("Max element: " + max); // Max element: 90
    }
}
```
## 20) How Do You Find the Minimum Element in an Array in Java?

### Code
```java
import java.util.*;

class MinimumElement {
    public static void main(String[] args) {
        int a[] = {12, 34, 90, 13, 45, 67, 3};
        System.out.println("List of elements: " + Arrays.toString(a)); // List of elements: [12, 34, 90, 13, 45, 67, 3]
        
        int min = a[0];
        for (int i = 0; i < a.length; i++) {
            if (a[i] < min) {
                min = a[i];
            }
        }
        System.out.println("Min element: " + min); // Min element: 3
    }
}
```
## 21) How Do You Find an Element in an Array in Java?

### Code
```java
import java.util.*;

class SearchElement {
    public static void main(String[] args) {
        int a[] = {12, 34, 90, 13, 45, 67, 3};
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter the element to search: ");
        int element = sc.nextInt();
        boolean elementFound = false;

        for (int i = 0; i < a.length; i++) {
            if (a[i] == element) {
                elementFound = true;
                break;
            }
        }

        if (elementFound) {
            System.out.println("Element Found");
        } else {
            System.out.println("Element Not Found");
        }
    }
}
```
## 22) How Do You Sort an Array in Ascending Order in Java?

### Code
```java
import java.util.*;

class SortInAsc {
    public static void main(String[] args) {
        int a[] = {12, 34, 90, 13, 45, 67, 3};
        System.out.println("Before Sorting: " + Arrays.toString(a)); // Before Sorting: [12, 34, 90, 13, 45, 67, 3]

        // Bubble sort algorithm
        for (int i = 0; i < a.length - 1; i++) {
            for (int j = i + 1; j < a.length; j++) {
                if (a[i] > a[j]) {
                    int temp = a[i];
                    a[i] = a[j];
                    a[j] = temp;
                }
            }
        }
        System.out.println("After Sorting: " + Arrays.toString(a)); // After Sorting: [3, 12, 13, 34, 45, 67, 90]
    }
}
```
## 23) How Do You Sort an Array in Descending Order in Java?

### Code
```java
import java.util.*;

class SortInDesc {
    public static void main(String[] args) {
        int a[] = {12, 34, 90, 13, 45, 67, 3};
        System.out.println("Before Sorting: " + Arrays.toString(a)); // Before Sorting: [12, 34, 90, 13, 45, 67, 3]

        // Bubble sort algorithm for descending order
        for (int i = 0; i < a.length - 1; i++) {
            for (int j = i + 1; j < a.length; j++) {
                if (a[i] < a[j]) {
                    int temp = a[i];
                    a[i] = a[j];
                    a[j] = temp;
                }
            }
        }
        System.out.println("After Sorting: " + Arrays.toString(a)); // After Sorting: [90, 67, 45, 34, 13, 12, 3]
    }
}
```
## 24) Find the First Repeating Character in a String

### Code
```java
class FirstRepeatingChar {
    public static void main(String[] args) {
        String str = "hello";
        char ch = '\0';
        boolean found = false;
        
        for (int i = 0; i < str.length() - 1; i++) {
            for (int j = i + 1; j < str.length(); j++) {
                if (str.charAt(i) == str.charAt(j)) {
                    ch = str.charAt(i);
                    found = true;
                    break;
                }
            }
            if (found) {
                break;
            }
        }
        
        if (found) {
            System.out.println("First Repeating Character: " + ch); // Output: First Repeating Character: l
        } else {
            System.out.println("No Repeating Characters Found"); // Output: No Repeating Characters Found
        }
    }
}
```
## 25) Count Occurrences of Characters in a String

### Code
```java
class FindNoOfOcc {
    public static void main(String[] args) {
        String str = "i love programming language";
        str = str.replace(" ", ""); // Remove spaces

        // Create an array to store the count of each character
        int[] count = new int[256]; // Array size 256 for all ASCII characters

        // Iterate over the string and count the occurrences of each character
        for (int i = 0; i < str.length(); i++) {
            count[str.charAt(i)]++;
        }

        // Print the count of each character
        System.out.println("Character occurrences:");
        for (int i = 0; i < 256; i++) {
            if (count[i] > 0) {
                System.out.println((char) i + ": " + count[i]);
            }
        }
    }
}
```
## 26) Print Even-Length Words from a String

### Code
```java
class PrintEven {
    public static void main(String[] args) {
        String str = "This is a java programming language";
        String[] words = str.split(" ");
        
        for (String word : words) {
            if (word.length() % 2 == 0) {
                System.out.println(word);
            }
        }
    }
}
This
is
java
language
```
## 27) Print Odd-Length Words from a String

### Code
```java
class PrintOdd {
    public static void main(String[] args) {
        String str = "This is a java programming language";
        String[] words = str.split(" ");
        
        for (String word : words) {
            if (word.length() % 2 != 0) {
                System.out.println(word);
            }
        }
    }
}
a
programming

```

## 28) Insert 2nd string in 1st string based on index
### Code
```java
class MergeTwoStrings {
   public static void main(String[] args) {
        String str1 = "Hello World";
        String str2 = "This is java programming ";
        int n = 5;
        String result = new String();
        for(int i=0;i<=str1.length()-1;i++){
            result += str1.charAt(i);
            if(i == n){
                result += str2;
            }
        }
        System.out.println("Result "+ result); // Result: HelloThis is java programming  World
    }
}
```
## 29) Check given string is anagram
### Code
```java
import java.util.*;

class Anagram {
    public static void main(String[] args) {
        String s1 = "hello";
        String s2 = "ollhe";
        boolean isAnagram = true;

        // Check if lengths are not equal
        if (s1.length() != s2.length()) {
            isAnagram = false;
        } else {
            char[] charArray1 = s1.toCharArray();
            char[] charArray2 = s2.toCharArray();
            Arrays.sort(charArray1);
            Arrays.sort(charArray2);

            String sortedS1 = new String(charArray1);
            String sortedS2 = new String(charArray2);

            // Compare the sorted strings
            for (int i = 0; i < sortedS1.length(); i++) {
                if (sortedS1.charAt(i) != sortedS2.charAt(i)) {
                    isAnagram = false;
                    break;
                }
            }
        }

        if (isAnagram) {
            System.out.println("Anagram"); // Anagram
        } else {
            System.out.println("Not Anagram");
        }
    }
}
```
## 30) Get Character form string
### Code
```java
class GetCharacter {
    public static void main(String[] args) {
        String str = "hello";
        int n = 1;
        System.out.println("Output :" +  str.charAt(n)); // Output : e
    }
}
```
## 31) Convert string to array
### Code
```java
import java.util.*;

class ConvertStringToArray {
    public static void main(String[] args) {
        String str = "hello world";
        String[] res = str.split(" ");
        System.out.println(Arrays.toString(res)); // [hello, world]
    }
}
```
## 32) Swap pair of character in java
### Code
```java
import java.util.*;

class SwapPairOfChar {
    public static void main(String[] args) {
        String str = "javaisproglang";
        System.out.println("Before swapping " + str);
        char[] ch = str.toCharArray();
        for(int i = 0; i < ch.length - 1; i += 2) {
            char temp = ch[i];
            ch[i] = ch[i + 1];
            ch[i + 1] = temp;
        }
        String res = new String(ch);
        System.out.println("After swapping " + res); // ajvaipsrolgagn
    }
}
```
## 33) Check is both arrays are equal or not?
### Code
```java
import java.util.*;

class ArrayEquality {
    public static void main(String[] args) {
        int[] a = {1, 3, 9, 5, 7, 8};
        int[] b = {1, 3, 5, 7, 8, 9};
        boolean isEqual = true;

        if (a.length != b.length) {
            isEqual = false;
        } else {
            Arrays.sort(a);
            Arrays.sort(b);
            for (int i = 0; i < a.length; i++) {
                if (a[i] != b[i]) {
                    isEqual = false;
                    break;
                }
            }
        }

        if (isEqual) {
            System.out.println("Both arrays are equal"); // Both arrays are equal
        } else {
            System.out.println("Both arrays are not equal");
        }
    }
}
```
## 34) Find armstrong no in java?
### Code
```java
import java.util.*;

class ArmstrongNo {
    public static void main(String[] args) {
        int result = 0;
        int d;
        int temp;

        Scanner sc = new Scanner(System.in);
        System.out.println("Please enter a number");
        int no = sc.nextInt();
        temp = no;

        while (no != 0) {
            d = no % 10;                 // Extract the last digit
            no = no / 10;                // Remove the last digit from no
            result = result + d * d * d;  // Add the cube of the digit to result
        }

        if (temp == result) {
            System.out.println("Given number is an Armstrong number");
        } else {
            System.out.println("Given number is not an Armstrong number");
        }
    }
}
```
## 35) Sum of digits?

### Code

```java
class SumOfDigits{
    public static void main(String args[]){
        int no = 80819;
        int sum = 0;
        int d;
        while (no != 0){
            d = no % 10;
            no = no / 10;
            sum += d;
        }
        System.out.println("Sum of digits "+ sum);
    }
}
```
## 36) Find duplicate from an array?

### Code

```java
class FindDuplicateInArray{
    public static void main(String args[]){
        int [] a = {1,2,4,2,6,9};
        boolean isDuplicate = false;
        int duplicate = 0;
        
        for(int i = 0 ; i < a.length; i++){
            for(int j = i + 1; j < a.length; j++){
                if(a[i] == a[j]){
                    isDuplicate = true;
                    duplicate = a[i];
                    break;
                }
            }
            if(isDuplicate){
                break;
            }
        }
        
        if(isDuplicate){
            System.out.println("Duplicate found " + duplicate); // Duplicate found 2
        } else {
            System.out.println("Duplicate not found");
        }
    }
}

```
## 37) Find second largest element in int array?

### Code

```java
import java.util.*;

class SecondLargestNoInArray {
    public static void main(String args[]) {
        int[] a = {2, 4, 7, 8, 6, 3, 1};
        
        for (int i = 0; i < a.length; i++) {
            for (int j = i + 1; j < a.length; j++) {
                if (a[i] < a[j]) {
                    int temp = a[i];
                    a[i] = a[j];
                    a[j] = temp;
                }
            }
        }
        
        System.out.println("Second largest " + a[1]); // Second largest 7
    }
}
```
## 38) Reverse no?

### Code

```java
import java.util.Scanner;

class ReverseNo {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter no");
        int no = sc.nextInt();
        int rev = 0;
        
        while (no != 0) {
            int d = no % 10;
            no = no / 10;
            rev = rev * 10 + d;
        }
        
        System.out.println("After reverse " + rev);
    }
}
```
## 39) Find a perfect no?

### Code

```java
import java.util.Scanner;

class PerfectNo {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter no");
        int no = sc.nextInt();
        int s = 0;
        
        for (int i = 1; i < no; i++) {
            if (no % i == 0) {
                s = s + i;
            }
        }
        
        if (s == no) {
            System.out.println("Perfect no");
        } else {
            System.out.println("Not a perfect no");
        }
    }
}
```
## 40) Find the factorial no

### Code

```java
import java.util.Scanner;

class FactorNo {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter no");
        int no = sc.nextInt();
        int s = 1;
        
        for (int i = 1; i <= no; i++) {
            s = s * i;
        }
        
        System.out.println("Factorial no " + s);
    }
}
```
## 41) Find power given x and y?

### Code

```java
import java.util.Scanner;

class FindPower {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter no");
        int x = sc.nextInt();
        int y = sc.nextInt();
        int p = 1;
        
        for (int i = 1; i <= y; i++) {
            p = p * x;
        }
        
        System.out.println("Power " + p);
    }
}
```
## 42) Pattern

### Code

```java
class Pattern {
    public static void main(String args[]) {
        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}
//Output
*
**
***
****
*****

```
## 43) Pattern

### Code

```java
class Pattern {
    public static void main(String args[]) {
        int p;
        for (int i = 1; i <= 5; i++) {
            p = 5;
            for (int j = 1; j <= i; j++) {
                System.out.print(p);
                p--;
            }
            System.out.println();
        }
    }
}

//Output

5
54
543
5432
54321

```

## 44) Pattern

### Code

```java
class Pattern {
    public static void main(String args[]) {
        int p;
        for (int i = 1; i <= 5; i++) {
            p = 1;
            for (int j = 1; j <= i; j++) {
                System.out.print(p);
                p++;
            }
            System.out.println();
        }
    }
}


//Output
1
12
123
1234
12345

```

## 46) Pattern

### Code

```java
class Pattern {
    public static void main(String args[]) {
        int p = 1;
        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(p);
                p++;
            }
            System.out.println();
        }
    }
}

//Output
1
23
456
78910
1112131415

```
## 46) Pattern

### Code

```java
class Pattern {
    public static void main(String args[]) {
        int p = 1;
        for (int i = 1; i <= 4; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(p);
                p++;
            }
            System.out.println();
        }
    }
}

//Output
1
23
456
78910

```

## 47) Pattern

### Code

```java
class Pattern {
    public static void main(String args[]) {
        char p = 'A';
        for (int i = 1; i <= 4; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(p);
            }
            System.out.println();
            p++;
        }
    }
}

//Output
A
BB
CCC
DDDD

```

## 48) Pattern

### Code

```java
class Pattern {
    public static void main(String args[]) {
        char p;
        for (int i = 1; i <= 4; i++) {
            p = 'E';
            for (int j = 1; j <= i; j++) {
                System.out.print(p);
                p--;
            }
            System.out.println();
        }
    }
}


//output
E
ED
EDC
EDCB

```

## 49) Pattern

### Code

```java
class Pattern {
    public static void main(String args[]) {
        for (int i = 5; i >= 1; i--) {
            for (int j = 1; j <= i; j++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}

//Output
*****
****
***
**
*

```
## 50) Pattern

### Code

```java
class Pattern {
    public static void main(String args[]) {
        for (int i = 5; i >= 1; i--) {
            int n = 1;
            for (int j = 1; j <= i; j++) {
                System.out.print(n);
                n++;
            }
            System.out.println();
        }
    }
}

//Output
12345
1234
123
12
1

```
## 51) Pattern

### Code

```java
class Pattern {
    public static void main(String args[]) {
        char c = 'A';
        for (int i = 5; i >= 1; i--) {
            for (int j = 1; j <= i; j++) {
                System.out.print(c);
            }
            System.out.println();
            c++;
        }
    }
}

//Output
AAAAA
BBBB
CCC
DD
E

```

## 52) Pattern

### Code

```java
class Pattern {
    public static void main(String args[]) {
        for (int i = 1; i <= 5; i++) {
            // Print spaces
            for (int k = 4; k >= i; k--) {
                System.out.print(" ");
            }
            // Print stars
            for (int j = 1; j <= i; j++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}

//Output
    *
   **
  ***
 ****
*****

```

## 53) Pattern

### Code

```java
class Pattern {
    public static void main(String args[]) {
        for (int i = 1; i <= 5; i++) {
            // Print spaces
            for (int k = 4; k >= i; k--) {
                System.out.print(" ");
            }
            // Print stars and spaces
            for (int j = 1; j <= i; j++) {
                System.out.print(" *");
            }
            System.out.println();
        }
    }
}

//Output
    *
   * *
  * * *
 * * * *
* * * * *

```
## 54) Pattern

### Code

```java
class Pattern {
    public static void main(String args[]) {
        for (int i = 5; i >= 1; i--) {
            // Print spaces
            for (int k = 4; k >= i; k--) {
                System.out.print(" ");
            }
            // Print stars
            for (int j = 1; j <= i; j++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}

//Output
*****
 ****
  ***
   **
    *

```
## 55) Pattern

### Code

```java
class Pattern {
    public static void main(String args[]) {
        for (int i = 5; i >= 1; i--) {
            // Print spaces
            for (int k = 4; k >= i; k--) {
                System.out.print(" ");
            }
            // Print stars and spaces
            for (int j = 1; j <= i; j++) {
                System.out.print(" *");
            }
            System.out.println();
        }
    }
}

//Output
 * * * * *
  * * * *
   * * *
    * *
     *
```
## 56) Pattern

### Code

```java
class Pattern {
    public static void main(String args[]) {
        for (int i = 4; i >= 1; i--) {
            int n = 1;
            // Print spaces
            for (int k = 3; k >= i; k--) {
                System.out.print(" ");
            }
            // Print numbers with spaces
            for (int j = 1; j <= i; j++) {
                System.out.print(" " + n);
                n++;
            }
            System.out.println();
        }
    }
}

//Output
 1 2 3 4
  1 2 3
   1 2
    1
```

## 57) Implement Pow(x, n)

### Question

Implement pow(x, n), which calculates x raised to the power n (i.e., \( x^n \)).

Example 1:

Input: x = 2.00000, n = 10  
Output: 1024.00000

Example 2:

Input: x = 2.10000, n = 3  
Output: 9.26100

Example 3:

Input: x = 2.00000, n = -2  
Output: 0.25000  
Explanation: \( 2^{-2} = \frac{1}{2^2} = \frac{1}{4} = 0.25 \)

### Code

```java
class Solution {
    public double myPow(double x, int n) {
        if (n == 0) {
            return 1.0;
        }
        double result = 1.0;
        // Converting to absolute number so that +ve and -ve cases can be handled
        long absNo = n > 0 ? n : -n;
        for (int i = 0; i < absNo; i++) {
            result *= x;
        }
        return n < 0 ? 1.0 / result : result;
    }
}
```
## 58) Print Sequence 1 to 100 without Loop

### Question

Print numbers from 1 to 100 without using a loop.

### Code

```java
class PrintSequence {
    public void print(int i) {
        if (i <= 100) {
            System.out.println(i);
            print(i + 1);
        }
    }

    public static void main(String args[]) {
        PrintSequence p = new PrintSequence();
        p.print(1);
    }
}
```
## 59) Find Square Root of Even Numbers without Using Stream

### Question

Find the square of even numbers in an array without using Java Streams.

### Code

```java
import java.util.*;

class SqRoot {
    public static void main(String args[]) {
        int a[] = {1, 2, 3, 4, 5, 6, 7, 8, 9};
        int result = 0;
        
        System.out.println(Arrays.toString(a));
        
        for (int i = 0; i < a.length; i++) {
            if (a[i] % 2 == 0) {
                result += a[i] * a[i];
            }
        }
        
        System.out.println(result); // Output here: 120
    }
}
```
## 60) Using Stream to Find Square of Even Numbers

### Question

Using Java Streams, find the square of even numbers in a list and calculate their total sum.

### Code

```java
import java.util.*;
import java.util.stream.Collectors;

class StreamExample {
    public static void main(String[] args) {
        ArrayList<Integer> l1 = new ArrayList<>();
        l1.addAll(Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9));
        
        System.out.println(l1);
        
        int total = 0;
        
        List<Integer> result = l1.stream()
                                 .filter(e -> e % 2 == 0)
                                 .map(e -> e * e)
                                 .collect(Collectors.toList());
        
        for (int res : result) {
            total += res;
        }
        
        System.out.println(total); // Output here: 120
    }
}
```
## 61) Filter Employees by Age Using Stream API

### Question

Given a list of employees with their names and ages, use Java Streams to filter and return the names of employees whose age is greater than or equal to 25.

### Code

```java
import java.util.*;
import java.util.stream.Collectors;

class StreamExample {
    public static void main(String[] args) {
        LinkedList<Employees> ls = new LinkedList<>();
        ls.add(new Employees("Jessy", 22));
        ls.add(new Employees("Walter", 50));
        ls.add(new Employees("Hank", 18));
        ls.add(new Employees("Skyler", 45));
        
        List<String> res = ls.stream()
                             .filter(e -> e.age >= 25)
                             .map(e -> e.name)
                             .collect(Collectors.toList());
        
        System.out.println(res); // Output here: [Walter, Skyler]
    }
}

class Employees {
    String name;
    int age;
    
    // Constructor to initialize name and age
    Employees(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    // Override toString method for meaningful output
    @Override
    public String toString() {
        return "Employees{name='" + name + "', age=" + age + "}";
    }
}
```
## 62) WAP in Java to demonstrate static and instance method references

### Code

```java
import java.util.function.Consumer;

class MethodReference {
    public static void staticMethod(String str) {
        System.out.println("Value Printed By Static Method " + str);
    }
    
    public void instanceMethod(String str) {
        System.out.println("Value Printed By Instance Method " + str);
    }
        
    public static void main(String[] args) {
        MethodReference mr = new MethodReference();
        
        // Using Static Method Reference
        Consumer<String> staticMethodValue = MethodReference::staticMethod;
        staticMethodValue.accept("Static Method Called");
        
        // Using Instance Method Reference
        Consumer<String> instanceMethodValue = mr::instanceMethod;
        instanceMethodValue.accept("Instance Method Called");
    }
}

```
## 63) How do you merge two unsorted arrays into single sorted array using Java 8 streams?

### Code

```java

import java.util.*;
import java.util.stream.*;
public class Main
{
	public static void main(String[] args) {
	    
	   Integer a[] = {11,42,31,40,25,69};
	   Integer b[] = {69,67,78,29,10};
	   
	   List<Integer> res = Stream.concat(Arrays.stream(a), Arrays.stream(b)).sorted().collect(Collectors.toList());
	    System.out.println(res);        //[10, 11, 25, 29, 31, 40, 42, 67, 69, 69, 78]
	}
}

```

## 64) How do you merge two unsorted arrays into single sorted array without duplicates?
### Code

```java
import java.util.*;
import java.util.stream.*;
public class Main
{
	public static void main(String[] args) {
	    
	   Integer a[] = {11,42,31,40,25,69};
	   Integer b[] = {69,67,78,29,10};
	   
	   List<Integer> res = Stream.concat(Arrays.stream(a), Arrays.stream(b)).sorted().distinct().collect(Collectors.toList());
	    System.out.println(res);		//[10, 11, 25, 29, 31, 40, 42, 67, 69, 78]
	}
}

```

## 65) How do you get three maximum numbers and three minimum numbers from the given list of integers?

### Code

```java

import java.util.*;
import java.util.stream.*;
public class Main
{
	public static void main(String[] args) {
	    
	    List<Integer> l1 = Arrays.asList(12,32,41,11,5,19,76,34,80,59,87,31);
	    
	    List<Integer> min3Val = l1.stream().sorted().limit(3).collect(Collectors.toList());
	    System.out.println("3 Min Values Are "+ min3Val);		// 3 Min Values Are [5, 11, 12]
	    
	    List<Integer> max3Val = l1.stream().sorted((a,b)-> b.compareTo(a)).limit(3).collect(Collectors.toList());
	    System.out.println("3 Max Values Are "+ max3Val);		// 3 Max Values Are [87, 80, 76]
	    
	    
	}
}
```

