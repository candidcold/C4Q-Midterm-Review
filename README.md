# Midterm Assessment Review
## Part 1: Java Questions

Review the questions from your past two exams, as those types of questions will be featured on the exam. If you were not present for the Friday night review, make sure you go over the questions featured in [JJ's midterm draft](https://github.com/C4Q/AC3.3/blob/master/lessons/midterm-design-patterns/FinalExamDraft.pdf).


If there's any other topic you need more practice in, do the example questions from [Oracle that are featured at the end of a chapter you find challenging](https://docs.oracle.com/javase/tutorial/java/).

If you want more practice reading tricky code, 
[here is a link](https://github.com/antoniorosario/TestPractice) to some questions made by Antonio in preparation for one of the past exams.

###### Writing Code

#####Problem 1
Given n of 1 or more, return the factorial of n, which is n * (n-1) * (n-2) ... 1. Compute the result recursively (without loops).

```
factorial(1) → 1
factorial(2) → 2
factorial(3) → 6
```

#####Problem 2
Given a string and an int n, return a string made of n repetitions of the last n characters of the string. You may assume that n is between 0 and the length of the string, inclusive.

```
repeatEnd("Hello", 3) → "llollollo"
repeatEnd("Hello", 2) → "lolo"
repeatEnd("Hello", 1) → "o"
```

#####Problem 3
Given the following signature, write code that finds all words (keys) in our dictionary, that have definition (value) matching the one passed in as a parameter.

```
public ArrayList<String> synonymOf(HashMap<String, String> dictionary, String definition);
```

#####Problem 4
We'll say that a "triple" in a string is a char appearing three times in a row. Return the number of triples in the given string. The triples may overlap.

```
countTriple("abcXXXabc") → 1
countTriple("xxxabyyyycd") → 3
countTriple("a") → 0
```

###### Other Practice Problems

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

#####Problem 6
How would you make a class that implements `SomethingIsWrong`?

What is the output of this program? What does <E> represent? Why is it used?

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

Suppose you changed `GenericStack<String>` to `GenericStack<Integer>` and you push `12` instead of `"Hello"`. What else about this code would have to change?

## Part 2: Android
Make an app from scratch that performs the following tasks

* Uses Retrofit to get information from [an API](http://www.bbc.co.uk/radio1/playlist.json) on the internet
* This API returns a **list** of **Playlists**. Each Playlist has a list of songs inside of it. 
* Display the information in a Fragment
	* This Fragment should display a RecyclerView of all of the playlists, not the songs in them. For example, it should display something along the lines of "A", "B", "Now That's What I Call Music 1999", "Kidz Bop 2016: **It's Lit Edition**", or whatever is returned.  
* **Bonus, do this if you want to.** When clicking on an item in that RecyclerView, it changes the Fragment (holding a RecyclerView) to actually show the songs in that Playlist. 

I will be going over how to do this on Thursday for review.
