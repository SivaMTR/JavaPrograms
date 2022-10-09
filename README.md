# Important Java Programs

Program 1 

Findout the occurence/duplicate of the words in given sentance. ex: "I am learning learning java java java programing".

Solution:
Points to remember:
1. Here the problem demands the count of each word. So we have to count the number of repeated words. So we have to use Hashmap. Hashmap stores key value pair. 
2. We have to fetch each word from the given string. For that we have to split the words by space. To split the words we have to use split() methods that returns the array of strings (It splits the given string into substrings).



import java.util.HashMap;
import java.util.Map;

public class CountWords {

	public static void main(String[] args) {
	
		String str = "I am learning learning java java java programming";
		Map<String, Integer> map = new HashMap<String, Integer>();
		Integer count = 1;
		//split method returns array of strings. 
		String[] arr = str.split(" ");
		for (int i = 0; i < arr.length; i++) {
			if (!map.containsKey(arr[i])) {
				map.put(arr[i], count);
			} else {
				map.put(arr[i], map.get(arr[i]) + 1);
			}
		}
		//To print output
		for (String x : map.keySet()) {
			System.out.println("The count of the word " + x + " is =" + map.get(x));
		}
	}
}



Program 2:

Findout specific characters occurence in the given string.

Solution:
We have to replace specific charecter 'a' with blank "" using replaceAll method and then substract the leght of actual string with result string lenght.


public class CountCharOccurence {
	
	public static void main(String args[]){
		
		String str = "java is object oriented language";
		
		int result = str.length()-str.replaceAll("a", "").length();
		
		System.out.println(result);
	}

}


Program 3:

Findout the duplicate character in the given string.

Solution:
1. Here we need to store key value pair (character and count) so we have to use Hashmap.
2. To convert given string into array of characters we have to use the toCharArray() method which is provided by String class. 

package ImpPrograms;

import java.util.HashMap;
import java.util.Map;

public class DuplicateChar {
	public static void main(String[] args) {

		String str = "Laptop";
		int count = 1;

		Map<Character, Integer> map = new HashMap<Character, Integer>();
		char[] arr = str.toCharArray();

		for (int i = 0; i < arr.length; i++) {
			if (!map.containsKey(arr[i])) {
				map.put(arr[i], count);
			} else {
				map.put(arr[i], map.get(arr[i]) + 1);
			}
		}
		for (Character x : map.keySet()) {
			if (map.get(x) > 1)
				System.out.println("The count of the duplicate char " + x + " is =" + map.get(x));
		}
	}
}


Program 4 :

Findout given two strings are ANAGRAM or not?

Solution:
1. First we have to convert given strings into lower case using toLowerCase() method and then use toCharArray() method to convert given string into array of characters.
2. Then sort the converted arrays using Array.sort() method. 
3. Compare two arrays.

import java.util.Arrays;

public class Anagram {
	public static void main(String[] args){
		
		String str1 = "army";
		String str2 = "mary";
		
		char[]  arr1 = str1.toLowerCase().toCharArray();
		char[]  arr2 = str2.toLowerCase().toCharArray();
		
		Arrays.sort(arr1);
		Arrays.sort(arr2);
		
		if(Arrays.equals(arr1, arr2)){
			System.out.println("Given strings are Anagram");
		}else{
			System.out.println("Given strings are not Anagrams");
		}
	}
}


Program 5:

Find out first non repeated character in the given string.

Solution:
1. We have to use LinkHashMap. It will maintain insertion order. 


import java.util.LinkedHashMap;

import java.util.Map;

import java.util.Map.Entry;

public class FirstNonRepeatedChar {
	public static void main(String[] args) {

		String str = "swiss";

		Map<Character, Integer> map = new LinkedHashMap<Character, Integer>();

		int count = 1;

		for (int i = 0; i < str.length(); i++) {

			if (!map.containsKey(str.charAt(i))) {
				map.put(str.charAt(i), count);
			} else {
				map.put(str.charAt(i), map.get(str.charAt(i)) + 1);
			}
		}

		for (Entry<Character, Integer> entry : map.entrySet()) {

			if (entry.getValue() == 1) {
				System.out.println("The first non repeated char is " + entry.getKey());
				break;
			}
		}

	}
}








