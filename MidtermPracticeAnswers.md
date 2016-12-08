#Midterm Review Answers

#####Problem 1
Given n of 1 or more, return the factorial of n, which is n * (n-1) * (n-2) ... 1. Compute the result recursively (without loops).

```
factorial(1) → 1
factorial(2) → 2
factorial(3) → 6
```

###### Solution:

```
public int factorial(int n) {
	if (n == 1) return 1;
	return factorial(n-1) * n;
}

```

#####Problem 2
Given a string and an int n, return a string made of n repetitions of the last n characters of the string. You may assume that n is between 0 and the length of the string, inclusive.

```
repeatEnd("Hello", 3) → "llollollo"
repeatEnd("Hello", 2) → "lolo"
repeatEnd("Hello", 1) → "o"
```

###### Solution:

```
public String repeatEnd(String word, int n) {
	String end = "";
	String answer = "";
	if (word.length() <= n) {
		end = word;
	} else {
		end = word.substring(word.length() - n);
	}
	
	for (int i = 0; i < n; i++) {
		answer += end;
	}
	return answer;
}
```

#####Problem 3
Given the following signature, write code that finds all words (keys) in our dictionary, that have definition (value) matching the one passed in as a parameter.

```
public ArrayList<String> synonymOf(HashMap<String, String> dictionary, String definition);
```

######Solution:

```
public ArrayList<String> synonymOf(HashMap<String, String> dictionary, String definition) {
	ArrayList<String> synonyms = new ArrayList<>();
	for (String word : dictionary.keySet()) {
		if (dictionary.get(word).equals(definition)) {
			synonyms.add(word);
		}
	}
	return synonyms;
}
```

#####Problem 4
We'll say that a "triple" in a string is a char appearing three times in a row. Return the number of triples in the given string. The triples may overlap.

```
countTriple("abcXXXabc") → 1
countTriple("xxxabyyyycd") → 3
countTriple("a") → 0
```

###### Solution:

```
public int countTriple(String str) {
  int tripleCount = 0;
  for (int i = 2; i < str.length(); i++) {
    if (str.charAt(i) == (str.charAt(i-1)) && str.charAt(i-1) == str.charAt(i-2)) {
      tripleCount++;
    }
  }
  return tripleCount;
}


```

#### Other Practice Problems

Below are some questions regarding topics people seem to have trouble with.

#####Problem 5
What is wrong with the following Interface? How would it be fixed?

```
public interface SomethingIsWrong {
    void aMethod(int aValue){
        System.out.println("Hi Mom");
    }
}
```

How would you make a class that implements `SomethingIsWrong`?

###### Solution:

In an `Interface` all you supply is the method signature, the function definition. You shouldn't be defining the method.

To make a class that implements `SomethingIsWrong` you would write `public MyClass implements SomethingIsWrong` and make sure you override `aMethod(int aValue)`.


#####Problem 6

What is the output of this program? What does `<E>` represent? Why is it used?

```
    import java.util.*;
    public class GenericStack<E> {
        Stack<E> stk = new Stack<E>();
        
	    public void push(E obj) {
            stk.push(obj);
	    }
	    
	    public E pop() {
            E obj = stk.pop();
	        return obj;
	    }
    }
    
    class Output {
        public static void main(String args[]) {
            GenericStack<String> gs = new GenericStack<String>();
            gs.push("Hello");
            System.out.println(gs.pop());
        }
    }
```

###### Solution

The output of this program is "Hello". `<E>` is a Generic type that takes the place of the type `GenericString` is created with. In this case it is `String`. In all places where `<E>` is present, it is replaced with `String` for that object when the program is running. If we were to change `GenericString<String>` to `GenericString<Integer>` none of our code inside `GenericString<E>` would have to change because the way we push and pop from our class `GenericString` is not dependent on the type we give it, thanks to the Generic type. 
