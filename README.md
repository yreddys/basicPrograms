

```java
// 1. Reverse a number / Palindrome

package com.numberss;

public class Reverse {
    public static void main(String[] args) {
        int num = 12345;
        int reverse = 0;
         while (num != 0) {
            // Extract the last digit of the original number
            int digit = num % 10;
            // Add the last digit to the reversed number,
            // shifting the existing digits of the reversed number one place to the left
            reverse = reverse * 10 + digit;
            // Remove the last digit from the original number
            num = num / 10;
        }
        System.out.println(reverse);
    }
}

package com.numberss;

public class reverseNumString {
    public static void main(String[] args) {
        int s=12345;
        String str=String.valueOf(s);
        String reverse=new StringBuilder(str).reverse().toString();
        int reverseNum=Integer.parseInt(reverse);
        System.out.println(reverseNum);
    }
}

 **Palindrome for String**

public class StringPalindrome {
	public static void main(String[] args) {
		String st = "RRR";
		String Reverse = "";
		for (int i = st.length() - 1; i >= 0; i--) {
			Reverse = Reverse + st.charAt(i);

		}
		if (st.equals(Reverse)) {
			System.out.println("Palindrome");

		} else {
			System.out.println("Not a palindrome");
		}
	}
}


// 2. Java program to find the 2nd largest number in an array

public class ThirdLargestNumberInAnArray {
    public static void main(String args[]) {
        int temp, size;
        int array[] = {10, 20, 25, 63, 96, 57};
        size = array.length;

        for(int i = 0; i<size; i++ ) {
            for(int j = i+1; j<size; j++) {
                if(array[i]>array[j]) {
                    temp = array[i];
                    array[i] = array[j];
                    array[j] = temp;
                }
            }
        }
        System.out.println("Third second largest number is:: "+array[size-2]);
    }
}

import java.util.Arrays;
public class LargestNumberSample {
    public static void main(String args[]) {
        int array[] = {10, 20, 25, 63, 96, 57};
        int size = array.length;
        Arrays.sort(array);
        System.out.println("sorted Array ::"+Arrays.toString(array));
        int res = array[size-2];
        System.out.println("2nd largest element is ::"+res);
    }
}

// 3. Find First non repeating character in a String

package com.arrays;

public class Hello {
    public static void main(String[] args) {
        String str="AABCDBE";
        for (int i=0;i<str.length();i++) {
            boolean unique=true;
            for (int j=0;j<str.length();j++) {
                if(i!=j&&str.charAt(i)==str.charAt(j)) {
                    unique=false;
                }
            }
            if(unique) {
                System.out.println(str.charAt(i));
                break;
            }
        }
    }
}

// 4. program to find MaxConsecutiveRepetition in String?

package com.arrays;

public class MaxConsecutiveRepetition {
    public static void main(String[] args) {
        String input = "aaabbbbcccccddd";
        printMaxConsecutiveRepetition(input);
    }

    public static void printMaxConsecutiveRepetition(String str) {
        for (int i = 0; i < str.length(); i++) {
            char currentChar = str.charAt(i);
            int count = 1;
            while (i + 1 < str.length() && str.charAt(i + 1) == currentChar) {
                count++;
                i++;
            }
            System.out.println(currentChar + "=" + count);
        }
    }
}

// 5. Reverse a String 

String str = "Hello";
// Approach -1
char[] chars = str.toCharArray();
for (int i = chars.length - 1; i >= 0; i--) {
    System.out.print(chars[i]);
}
// Approach -2
for (int i = str.length() - 1; i >= 0; i--) {
    System.out.println(str.charAt(i));
}
// Approach -3
StringBuffer sb = new StringBuffer(str);
System.out.println(sb.reverse());
// Approach -4
StringBuilder sb1= new StringBuilder();
System.out.println(sb1.reverse());

// 6. Removing Duplicates from String

public static void main(String[] args) {
    String str = "HelloHello";
    // Approach -1
    StringBuilder sb = new StringBuilder();
    str.chars().distinct().forEach(c -> sb.append((char) c));
    System.out.println(sb);
    // Approach -2
    StringBuilder sb2 = new StringBuilder();
    for (int i = 0; i < str.length(); i++) {
        char ch = str.charAt(i);
        int indx = str.indexOf(ch, i + 1);
        if (indx == -1) {
            sb2.append(ch);
        }
    }
    System.out.println(sb2);
    // Approach -3
    char[] arr = str.toCharArray();
    StringBuilder sb3 = new StringBuilder();
    for (int i = 0; i < arr.length; i++) {
        boolean repeated = false;
        for (int j = i + 1; j < arr.length; j++) {
            if (arr[i] == arr[j]) {
                repeated = true;
                break;
            }
        }
        if (!repeated) {
            sb3.append(arr[i]);
        }
    }
    System.out.println(sb3);
    // Approach -4
    StringBuilder sb4 = new StringBuilder();
    Set<Character> set = new LinkedHashSet();
    for (int i = 0; i < str.length(); i++) {
        set.add(str.charAt(i));
    }
    for (Character c : set) {
        sb4.append(c);
    }
    System.out.println(sb4);
}

// Approach -5
Set<Character> seen = new HashSet<>();
Set<Character> duplicates = new HashSet<>();
for (char c : str.toCharArray()) {
    if (!seen.add(c)) { 
        duplicates.add(c);
    }
}
System.out.println("Duplicate characters: " + duplicates);

// 7. Reverse each Word In Given String

public class reverseWord {
    public static void main(String[] args) {
        String str = "Reddy sekhar";
        String output="";
        String[] words = str.split(" ");
        for(String word:words) {
            String revWord="";
            for(int i=word.length()-1;i>=0;i--) {
                revWord=revWord+word.charAt(i);
            }
            output=output+revWord+"";
        }
        System.out.println(output);
    }
}

// 8. To Find Longest SubString without Repeating Characters

package com.problems;

import java.util.LinkedHashMap;
import java.util.Map;

public class longestSubstringWithoutRepeating {
    static void longestSubstring(String s) {
        String LongestSubstring = null;
        int LongestSubstringLength = 0;
        Map<Character, Integer> map = new LinkedHashMap<>();
        char[] arr = s.toCharArray();
        for (int i = 0; i < arr.length; i++) {
            char ch = arr[i];
            if (!map.containsKey(ch)) {
                map.put(ch, i);
            } else {
                i = map.get(ch);
                map.clear();
            }
            if (map.size() > LongestSubstringLength) {
                LongestSubstringLength = map.size();
                LongestSubstring = map.keySet().toString();
            }
        }
        System.out.println(LongestSubstring);
        System.out.println(LongestSubstringLength);
    }

    public static void main(String[] args) {
        longestSubstring("abcabc");
   

 }
}

// 9. Find the Length of Last Word in String

public class findTheLengthOfLastWord {
    static int lastWordLength(String str) {
        int count = 0;
        for (int i = str.length() - 1; i >= 0; i--) {
            char c = str.charAt(i);
            if (c != ' ') {
                count++;
            } else {
                break;
            }
        }
        return count;
    }

    public static void main(String[] args) {
        int countLastWodrds = lastWordLength("Hello buddy i am here");
        System.out.println(countLastWodrds);
    }
}

// 10. Find the Longest Word in String

package com.problems;

public class longestWord {
    static String LongestWord(String str) {
        String longWord;
        String arr[] = str.split(" ");
        longWord = arr[0];
        for (String a : arr) {
            if (longWord.length() < a.length()) {
                longWord = a;
            }
        }
        return longWord;
    }

    public static void main(String[] args) {
        String s = LongestWord("Hello Reddysekhar How are you");
        System.out.println(s);
    }
}

// 11. Find the Length of Each Word in String

package longestWord;

class lengthOfeachWord {
    public static void lengthofeachword(String str) {
        StringBuilder word = new StringBuilder();
        str=str+" ";
        for(int i=0;i<str.length();i++) {
            char c = str.charAt(i);
            if(c!=' ') {
                word.append(c);
            } else {
                if(word.length()>0) {
                    System.out.println(word+" "+word.length());
                    word.setLength(0);
                }
            }
        }
    }
    public static void main(String[] args) {
        lengthofeachword("i am an aiExpert");
    }
}

// 12. Find the Longest Word in String and Count

class maxLengthInString {
    public static void maxLengthInString(String str) {
        StringBuilder word = new StringBuilder();
        str = str + " ";
        int maxLength = 0;
        String maxWord = "";
        for (int i = 0; i < str.length(); i++) {
            char c = str.charAt(i);
            if (c != ' ') {
                word.append(c);
            } else {
                if (word.length() > 0) {
                    System.out.println(word + " " + word.length());
                    if (word.length() > maxLength) {
                        maxLength = word.length();
                        maxWord = word.toString();
                    }
                    word.setLength(0);
                }
            }
        }
        System.out.println("Maximum length word: " + maxWord + ", Length: " + maxLength);
    }

    public static void main(String[] args) {
        maxLengthInString("i am an aiExpert");
    }
}


// 13 . program to find all permutations of a string 

package com.march15;

public class permutations {
	static void StringPermutations(String s) {

		System.out.println("Permutations of string :" + s);
		Stringpermutations("", s);

	}

	private static void Stringpermutations(String str, String input) {

		if (input.length() == 0) {
			System.out.println(str);

		} else {

			for (int i = 0; i < input.length(); i++) {

				Stringpermutations(str + input.charAt(i),
						input.substring(0, i) + input.substring(i + 1, input.length()));

			}
		}
	}

	public static void main(String[] args) {
		StringPermutations("How");
	}
}

// 13 . Java program to find the first and last index of a given integer in an array?
// 14. Program to  find the common values between two lists using Java 8 streams ?
// 15. Can you  write a program that counts the number of zeros in an array?


Input : {0, 2, 0, 4, 0, 6, 0}
Output: 4
```

