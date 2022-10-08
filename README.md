# Important Java Programs

1. Findout the occurence of the words in given sentance. ex: "I am learning learning java java java programing".

Solution:
Points to remember:
1. Here the problem demands the count of each word. So we have to count the number of repeated words. So we have to use Hashmap. Hashmap stores key value pair. 
2. We have to fetch each word from the given string. For that we have to split the words by space. To split the words we have to use split() methods that returns the array of strings (It splits the given string into substrings).

################################################# Program ########################################################
import java.util.HashMap;
import java.util.Map;

public class CountWords {

	public static void main(String[] args) {

		String str = "I am learning learning java java java programming";

		Map<String, Integer> map = new HashMap<String, Integer>();
		Integer count = 1;
		String[] arr = str.split(" ");

		for (int i = 0; i < arr.length; i++) {

			if (!map.containsKey(arr[i])) {
				map.put(arr[i], count);
			} else {
				map.put(arr[i], map.get(arr[i]) + 1);
			}
		}
		for (String x : map.keySet()) {
			System.out.println("The count of the word " + x + " is =" + map.get(x));
		}

	}

}




