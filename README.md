# concurrency-parallelism-project-7-solved
**TO GET THIS SOLUTION VISIT:** [Concurrency-Parallelism Project 7 Solved](https://www.ankitcodinghub.com/product/concurrency-parallelism-project-7-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;94290&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;Concurrency-Parallelism Project 7 Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
<div class="page" title="Page 1">
<div class="layoutArea">
<div class="column">
With this lab assignment you shall understand the tradeoffs between the costs and benefits of using different locking strategies.

1 Introduction

In this project you are given a running Java application, available at

<pre>git clone https://bitbucket.org/joaomlourenco/concurrent_hashmap.git
</pre>
This application launches multiple threads (the number of threads is specified as the second command line argument) operating over a shared data structure (a hash map with collision lists), by inserting, removing and looking up for elements. After a certain time (specified in milliseconds as the first command line argument) the application prints some statistics and terminates.

You may import the project to Eclipse and work from there. If you prefer to work from the command line, go to the application “root directory” (you shall have three subdirecto- ries: “bin”, “src”, and “resources”) and run the command below.

<pre>find src -name ’*.java’ -print | xargs javac -d bin
</pre>
To run the application, execute the command below, where the first argument is the time the application will run (in milliseconds) and the second is the number of threads. The output of the execution is typeset in italic.

</div>
</div>
<div class="layoutArea">
<div class="column">
<pre>java -cp bin cp/articlerep/Main 1000 1</pre>
</div>
</div>
</div>
<div class="page" title="Page 2">
<div class="layoutArea">
<div class="column">
And you will get an output similar to the following

<pre>Starting application...
Total operations: 4644330
Total successful puts: 585344 (13%)
Total successful removes: 575931 (12%)
Total successful gets: 1151131 (25%)
Throughput: 4644330 ops/sec
Finished application.
</pre>
2 Lab Work

2.1 Add automatic validation

Nearby line 82 of the Main.java file you can find a sanity check, which implements some basic verification of the final state of out concurrent hash map. However, this validation is too weak and passing this validation does not mean that there were no concurrency conflicts.

Add a more elaborated automatic validation to your program. For this you must:

<ol>
<li>Think about the invariants of the hash map and of the application;</li>
<li>Identify which of those invariants may be broken when running the application with multiple threads;</li>
<li>Change the current sanity check to implement checks for the identified invariants. Depending on the additional invariants you plan to check, it may be necessary to change the interface and the implementation of the hash map to include an additional method “validate()” to check the invariants of the hash map data structure and report to the caller;</li>
</ol>
2.2 Implement different locking strategies to fix the concurrency issues

Create four different implementations of the hash map, each one using a different locking strategy:

1. Create a solution that implements a coarse grain locking strategy using the Java construct synchronized. With this implementation there is a single global lock and only one thread at a time will be allowed to access the hash map.

2

</div>
</div>
<div class="layoutArea">
<div class="column">
Before you start fixing the concurrency issues in the hash map, be sure that you develop a set of strong and solid tests, and that your program fails those tests frequently.

</div>
</div>
</div>
<div class="page" title="Page 3">
<div class="layoutArea">
<div class="column">
<ol start="2">
<li>Create a solution that implements a coarse grain locking strategy using a single plain (exclusive) lock from the java.util.concurrent.locks package. With this implementation there is also a single global lock and only one thread at a time will be allowed to access the hash map.</li>
<li>Create a solution that implements a coarse grain locking strategy using a single read-write lock from the java.util.concurrent.locks package. With this imple- mentation, many lookup operations (get) may access the hash map simultaneously, but update operations (put and remove) must do it one at a time.</li>
<li>Create a solution that implements a medium grain locking strategy (i.e., one lock for each collision list of the hash map) using plain (exclusive) locks from the java.util.concurrent.locks package. With this implementation, many operations may access the hash map simultaneously as long as they are operating on different collision lists.</li>
<li>Create a solution that implements a medium grain locking strategy (i.e., one lock for each collision list of the hash map) using read-write locks from the java.util.concurrent.locks package. With this implementation, many operations may access the hash map simultaneously as long as they are operating on different collision lists or they are multiple get operations on the same collision list.</li>
<li>OPTIONAL: Create a solution that implements a fine grain locking strategy, namely hand-over-hand, optimistic and/or lazy sychronization, to control the concurrent accesses to the hash map collision lists.</li>
</ol>
2.3 Evaluate the effectiveness of each locking strategy

Run tests to evaluate the correctness of each of your solutions from above. If your imple- mentations prove correct, then run ore tests to evaluate the scalability of the application when you increase the number of threads. Run experiments with 1,2,4,…,N threads, where N is the double of the number of processors/cores you have available in your deve- lopment computer.

NOTE: if you are using some kind of vitualized environment, please be sure that you have more than one processor assigned to your virtual execution environment.

2.4 Acquire a deeper understand of your Java program

Install the “visualvm” (https://visualvm.github.io/features.html) tool with apt get install visualvm

and then use this tools to analyse the multiple versions of the concurrent hash map.

3

</div>
</div>
</div>
<div class="page" title="Page 4">
<div class="layoutArea">
<div class="column">
2.5 To Think About. . .

The sequential (unprotected) version is much faster than any lock-based solution. Will any of your solutions ever exhibit a speedup instead of a slowdown? How many processors do you need for that?

</div>
</div>
<div class="layoutArea">
<div class="column">
4

</div>
</div>
</div>
