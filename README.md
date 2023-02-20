# Writing and Reading Methods

## Learning Goals

- Learn how to read methods.
- Discover how to write methods that take no parameters and have no return
  value.

## Reading and Understanding Methods

Now that we know a little about methods, let's look at how to call methods and
read them!

Let us consider a scenario where we want to greet some neighbors to a
neighborhood block party!

Consider the following code:

```java
public class MethodExample {

    public static void welcome() {
        System.out.println("Welcome neighbors!");
    }

    public static void main(String[] args) {
        welcome();
    }
}
```

In the code above, we have not only our `main()` method, but we also have
another method called `welcome()`. Let's look at the method header of the
`welcome()` method so we can understand what this method does:

![method-header](https://curriculum-content.s3.amazonaws.com/java-mod-1/methods-without-parameters/method-header-no-parameters.png)

As we mentioned in the last lesson, every method has an access modifier. We'll
learn more about access modifiers later on. For now, know that in order to
write a method, it needs to have an access modifier present. All of our methods
in this module will have a `public` access modifier, just like the `main()`
method. We'll also use it in conjunction with the non-access modifier, `static`.
We'll cover `static` and other non-access modifiers in the next module.

The `void` keyword means that this method will **not** return anything. But
every method (except for some special methods) need to specify a return type.
If we see a method that has a `void` return type, this means it will not return
anything. We'll look at methods that do return something in a couple of lessons.
For this lesson, we'll focus on methods that do not return anything, so we can
familiarize ourselves with reading, writing, and calling methods.

This method has a name called `welcome`. The method name always comes after the
access modifiers and return type.

We might also notice the `()`. Since there is nothing between the parentheses,
we can say that this method does not take in any parameters. In this lesson, we
won't worry about parameters just yet.

To summarize, the `welcome()` method is called `welcome`. It does not return
anything nor does it take in any parameters for the method to function.

Each method has its own **scope**, which is defined by the curly braces `{}`.
The statements within the curly braces are grouped together. This means, any
time we call the method, `welcome()`, all the statements between the method's
curly braces will be executed.

Notice that the method is defined **outside** the `main()` method. This is so
we can actually _call_ the method within the `main()` method. The `welcome()`
method will not be invoked or executed until we call it elsewhere in the code.
As we can see, we call a static method by simply writing out the method name
and its parameters where we want to execute the method's block statements.

Let us see what happens when we run this method:

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=public%20class%20Main%20%7B%0A%0A%20%20%20%20public%20static%20void%20welcome%28%29%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Welcome%20neighbors!%22%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20%20%20welcome%28%29%3B%0A%20%20%20%20%7D%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=1&heapPrimitives=nevernest&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

If we click "Next >", we will see the execution jumps up to the first line in
the `welcome()` method! When we continue clicking the "Next >" button, we will
see it print out the message "Welcome neighbors!" and then return to the bottom
of the `main()` method.

Let's add another method to this example:

```java
public class MethodExample {
    public static void welcome() {
        System.out.println("Welcome neighbors!");
    }

    public static void announce() {
        System.out.println("Food will be served in 15 minutes.");
    }

    public static void main(String[] args) {
        welcome();
    }
}
```

We have created another method called `announce()`. Like the `welcome()` method,
it also will not return anything and does not take in any parameters. We can see
this by looking at the method header again:

`public static void announce()`

<details>
    <summary>If we run this program now, what will the output be?</summary>

  <p>Answer: <br>
     <p>Welcome neighbors!</p>
  </p>

  <p>Even though we added another method, <code>announce()</code>, we never call it in the <code>main()</code> method.</p>
  <p>If we want to see the message "Food will be served in 15 minutes." we need to call the method within the <code>main()</code> method. Otherwise, it will never be invoked.</p>

</details>

Let's add one more method to this example:

```java
public class MethodExample {
    public static void welcome() {
        System.out.println("Welcome neighbors!");
    }

    public static void announce() {
        System.out.println("Food will be served in 15 minutes.");
    }

    public static void farewell() {
        System.out.println("Thanks for coming neighbors!");
        System.out.println("See you next year!");
    }

    public static void main(String[] args) {
        welcome();
        farewell();
    }
}
```

Notice the `farewell()` method has now been added. Like the other two methods,
it also will not return anything and does not take in any parameters. We know
this by looking at the method header:

`public static void farewell()`

This time, the `farewell()` method contains 2 statements. This means, every time
the `farewell()` method is called, it will execute both of those statements.

<details>
    <summary>If we run this program now, what will the output be?</summary>

  <p>Answer: <br>
     <p>Welcome neighbors!<br>Thanks for coming neighbors!<br>See you next year!</p>
  </p>

  <p>Notice we still haven't called the <code>announce()</code> method within the <code>main()</code> method. Therefore, this method is never invoked still.</p>
  <p>Since the <code>welcome()</code> method is called first, it will execute that method and then call the <code>farewell()</code> method and execute the two statements within that method block.</p>
</details>

To visualize this program, see the browser-based Java Visualizer link
[here](https://pythontutor.com/visualize.html#code=public%20class%20MethodExample%20%7B%0A%20%20%20%20public%20static%20void%20welcome%28%29%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Welcome%20neighbors!%22%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20public%20static%20void%20announce%28%29%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Food%20will%20be%20served%20in%2015%20minutes.%22%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20public%20static%20void%20farewell%28%29%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Thanks%20for%20coming%20neighbors!%22%29%3B%0A%20%20%20%20%20%20%20%20System.out.println%28%22See%20you%20next%20year!%22%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20%20%20welcome%28%29%3B%0A%20%20%20%20%20%20%20%20farewell%28%29%3B%0A%20%20%20%20%7D%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false).

## Comprehension Check: Reading Methods

Consider the following code:

```java
public class GreetingExample {
    public static void greeting() {
        System.out.println("Hello world!");
    }
}
```

<details>
    <summary>Describe the method above by looking at the method header.</summary>

  <p>Answer: <br>
     <p>The <code>greeting()</code> method does not take in any parameters nor does it return anything.</p>
  </p>
</details>

<details>
    <summary>Does this program output anything?</summary>

  <p>Answer: <br>
     <p>No. The method <code>greeting()</code> is never invoked. We are also missing a <code>main()</code> method.</p>
  </p>
</details>

<details>
    <summary>How would you call this method from the <code>main()</code> method?</summary>

  <p>Answer: <br>
     <p><code>greeting();</code></p>
  </p>

  <p>We call a static method by writing out the method name and its parameters where we want to execute the method's block statements.</p>
</details>

Consider the following code:

```java
public class SongExample {

    public static void chorus() {
        System.out.println("Twinkle twinkle little star");
        System.out.println("How I wonder what you are");
    }

    public static void song() {
        chorus();
        System.out.println("Up above the world so high");
        System.out.println("Like a diamond in the sky");
        chorus();
    }

    public static void main(String[] args) {
        song();
    }
}
```

<details>
    <summary>What does this program output?</summary>

  <p>Answer: <br>
     <p>Twinkle twinkle little star<br>How I wonder what you are<br>Up above the world so high<br>Like a diamond in the sky<br>Twinkle twinkle little star<br>How I wonder what you are</p>
  </p>

  <p>In this program, we call the <code>song()</code> method from the <code>main()</code> method. This will execute all the statements within the <code>song()</code> method's code block.</p>
  <p>Notice that the <code>song()</code> method calls the <code>chorus()</code> method twice within its own code block! Methods can call each other!</p>
  <p>See the link below to step through the code above:</p>
  <a href="https://pythontutor.com/visualize.html#code=public%20class%20SongExample%20%7B%0A%0A%20%20%20%20public%20static%20void%20chorus%28%29%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Twinkle%20twinkle%20little%20star%22%29%3B%0A%20%20%20%20%20%20%20%20System.out.println%28%22How%20I%20wonder%20what%20you%20are%22%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20public%20static%20void%20song%28%29%20%7B%0A%20%20%20%20%20%20%20%20chorus%28%29%3B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Up%20above%20the%20world%20so%20high%22%29%3B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Like%20a%20diamond%20in%20the%20sky%22%29%3B%0A%20%20%20%20%20%20%20%20chorus%28%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20%20%20song%28%29%3B%0A%20%20%20%20%7D%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false">Browser-based Java Visualizer of SongExample</a>
</details>


## Writing Methods

Now that we know how to read methods better, let's start writing methods!

Consider we want to write a method to show a kid riding a bike:

```java
public class BikeExample {

    public static void main(String[] args) {

    }
}
```

Let's start by creating a method called `ride`. The `ride` method will not
return anything nor will it take in any parameters.

<details>
    <summary>What would the method header look like for this described method?</summary>

  <p>Answer: <br>
     <p><code>public static void ride()</code></p>
  </p>

</details>

<details>
    <summary>Where will we write method?</summary>

  <p>Answer: <br>
     <p>Outside the <code>main()</code> method.</p>
  </p>

  <p>This is so we can eventually call the method.</p>
</details>

We want this method to print the message: "Whee! Look at me riding my bike!".

<details>
    <summary>What would the body of this method look like?</summary>

  <p>Answer: <br>
     <p><code>System.out.println("Whee! Look at me riding my bike!");</code></p>
  </p>

  <p>This one statement would go within the curly braces of the <code>ride()</code> method.</p>
</details>

<details>
    <summary>How do we call our new method?</summary>

  <p>Answer: <br>
     <p>We call it within the <code>main()</code> method.</p>
     <p>We'll write <code>ride();</code> in the <code>main()</code> method to call the <code>ride()</code> method.</p>
  </p>

  <p>We call a static method by writing out the method name and its parameters where we want to execute the method's block statements.</p>
</details>

<details>
    <summary>What does the final version of the program look like?</summary>

  <p>Answer: <br>
     <img src="https://curriculum-content.s3.amazonaws.com/java-mod-1/methods-without-parameters/bike-example.png">
  </p>

</details>
<details>
    <summary>What is the output when we run this program?</summary>

  <p>Answer: <br>
     <p><code>System.out.println("Whee! Look at me riding my bike!");</code></p>
  </p>

  <p>This one statement would go within the curly braces of the <code>ride()</code> method.</p>
</details>


## Conclusion

We now know how to read, call, and write methods that return nothing and take in
no parameters. We also better understand how methods work by stepping through
the code. In the next lesson, we'll learn about reading, calling, and writing
methods with parameters.
