Download Link: https://assignmentchef.com/product/solved-csci-1200-homework-6-inverse-word-search-recursion
<br>



In this homework we will build an inverse word search program using the techniques of recursion. The goal is to construct a grid of letters that one can search to find specific words. Understanding the non-linear word search program from Lectures 13 &amp; 14 will be helpful in thinking about how you will solve this problem. We strongly urge you to study and play with that program, including tracing through its behavior using a debugger or cout statements or both. <em>Please read the entire handout before beginning your implementation. </em><strong>Your Tasks</strong>

For this assignment, you will be given the dimensions (width and height) of a word search puzzle, a set of words that should appear in the grid (forwards, backwards, up, down, or along any diagonal), and optionally a set of words that should not appear anywhere in the grid. Each grid cell will be assigned one of the 26 lowercase letters. Note that unlike the non-linear word search problem we discussed in class, we will only allow words that appear in a straight line (including diagonals). Your task is to output all unique word search grids that satisfy the requirements. Rotations and mirroring of the board will be considered unique solutions.

Your program should expect three command line arguments, the name of the input file, the name of the output file, and a string:

inverse_word_search.exe puzzle2.txt out2.txt one_solution inverse_word_search.exe puzzle2.txt out2.txt all_solutions

The third argument indicates whether the program should find all solutions, or just one solution. Here’s an example of the input file format:

4 4

+ arts

+ arid

+ east

+ rest

<ul>

 <li>ear – at</li>

 <li>sit</li>

</ul>

The first line specifies the width and height of the grid. Then each line that follows contains a character and a word. If the character is ’+’, then the word must <em>appear </em>in the grid. If the character is ’-’, then the word must <em>not appear </em>in the grid. For this first example we show an incorrect solution on the left. Though it contains the 4 required words, it also contains two of the forbidden words. The solution on the right is a fully correct solution. This particular problem has 8 solutions including rotations and reflections.

Below is a second example that specifies only positive (required) words. This puzzle has 4 solutions including rotations and reflections.

5 3

+ echo

+ baker

+ apt

+ toe

+ ore

+ eat

+ cap

When asked to find all solutions, your program should first output the number of solutions and then an ASCII representation for each solution. See the example output on the course webpage. You should follow this output closely, however your solutions may be listed in a different order. When asked to find just one solution, your program should just output the first legal solution it finds (it does not need to count the number of solutions). If the puzzle is impossible your program should output “No solutions found”.

To implement this assignment, you must use recursion in your search. First you should tackle the problem of finding and outputting one legal solution to the puzzle (if one exists). Nearly full credit will be given for submissions that do this correctly. Full credit will be given to programs that find <em>all </em>of the solutions.

<h1>Algorithm Analysis</h1>

For larger, more complex examples, this is a really hard problem. Your program should be able to handle the small puzzles we have created in a reasonable about of time. You should make up your own test cases as well to understand this complexity. Include these test cases with your submission (they will be graded). Summarize the results of your testing, which test cases completed successfully and the approximate “wall clock time” for completion of each test. The UNIX/cygwin time command can be prepended to your command line to estimate the running time: time inverse_word_search.exe puzzle1.txt out1.txt

Once you have finished your implementation and testing, analyze the performance of your algorithm using order notation. What important variables control the complexity of a particular problem? The width &amp; height of the grid (<em>w </em>and <em>h</em>), the number of required words (<em>r</em>), the number of forbidden words (<em>f</em>), the number of letters in each word (<em>l</em>), the number of solutions (<em>s</em>)? In your <em>plain text </em>README.txt file, write a concise paragraph (<em>&lt; </em>200 words) justifying your answer. Also include a simple table summarizing the running time and number of solutions found by your program on each of the provided examples. <em>Note: Its ok if your program cant solve the biggest puzzles in a reasonable amount of time.</em>

<strong>IMPORTANT</strong>: All students are required to submit their program to the Homework 6 contest (see below). Extra credit will be awarded for programs that have a strong performance in the contest. You must do this assignment on your own, as described in the <a href="http://www.cs.rpi.edu/academics/courses/spring17/ds/academic_integrity.php">“Collaboration Policy &amp; Academic Integrity”</a> handout. If you did discuss this assignment, problem solving techniques, or error messages, etc. with anyone, please list their names in your README.txt file.

2

<h1>Homework 6 Inverse Word Search Contest Rules</h1>

<ul>

 <li>Contest submissions are a separate homework submission. Contest submissions are due Sunday Apr 2nd at 11:59pm. You may not use late days for the contest. (The regular homework deadline is Thursday Mar 23rd at 11:59pm and late days are allowed for the regular homework submissions.)</li>

 <li>You may submit the same code for both the regular homework submission and the contest. Or you may make a small or significant change for the contest.</li>

 <li>Contest submissions do not need to use recursion.</li>

 <li>Contest submissions must follow the output specifications and match the formatting of the examples posted on the course webpage.</li>

 <li>We will compile your code with optimizations enabled (g++ -O3 *.cpp) and run all submitted entries on the homework server. Programs that do not compile, or do not complete the basic tests in a reasonable amount of time with correct output, will not receive extra credit.</li>

 <li>Programs must be single-threaded and single-process.</li>

 <li>We will run your program by <em>redirecting </em>std::cout to a file and measure performance with the UNIX time For example:</li>

</ul>

time paint_by_pairs.out puzzle1.txt &gt; out_puzzle1.txt

time paint_by_pairs.out puzzle1.txt find_all_solutions &gt; out_puzzle1_all.txt

<ul>

 <li>You may want to use a <em>C++ code profiler </em>to measure the efficiency of your program and identify the portions of your code that consume most of the running time. A profiler can confirm your suspicions about what is slow, uncover unexpected problems, and focus your optimization efforts on the most inefficient portions of the code.</li>

 <li>We will be testing with and without the optional command line argument find all solutions and will highlight the most correct and the fastest programs.</li>

 <li>You may submit up to two interesting new test cases for possible inclusion in the contest. Name these tests smithj 1.txt and smithj txt (where smithj is your RCS username). Extra credit will be awarded for interesting test cases that are used in the contest. Caution: Dont make the test cases so difficult that your program cannot solve them in a reasonable amount of time!</li>

 <li>In your README contest.txt file, describe the optimizations you implemented for the contest, describe your new test cases, and summarize the performance of your program on all test cases. • Extra credit will be awarded based on overall performance in the contest</li>

</ul>


