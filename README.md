Download Link: https://assignmentchef.com/product/solved-cmsc430-project-1
<br>
The first project involves modifying the attached lexical analyzer and the compilation listing generator code. You need to make the following modifications to the lexical analyzer, scanner.l:

<ol>

 <li>A new token <sub>ARROW</sub> should be added for the two character punctuation symbol <sub>=&gt;</sub>.</li>

 <li>The following reserved words should be added:</li>

</ol>

case, else, endcase, endif, if, others, real, then, when




Each reserved words should be a separate token. The token name should be the same as the lexeme, but in all upper case.

<ol start="3">

 <li>Two additional logical operators should be added. The lexeme for the first should be <sub>or</sub> and its token should be <sub>OROP</sub>. The second logical operator added should be <sub>not</sub> and its token should be <sub>NOTOP</sub>.</li>

 <li>Five relational operators should be added. They are <sub>=</sub>, <sub>/=</sub>, <sub>&gt;</sub>, <sub>&gt;=</sub> and <sub>&lt;=</sub>. All of the lexemes should be represented by the single token <sub>RELOP</sub>.</li>

 <li>One additional lexeme should be added for the <sub>ADDOP</sub> It is binary <sub>–</sub>.</li>

 <li>One additional lexeme should be added for the <sub>MULOP</sub> It is<sub>/</sub>.</li>

 <li>A new token <sub>REMOP</sub> should be added for the remainder operator. Its lexeme should be</li>

</ol>

rem.

<ol start="8">

 <li>A new token <sub>EXPOP</sub> should be added for the exponentiation operator. Its lexeme should be <sub>**</sub>.</li>

 <li>A second type of comment should be added that begins with <sub>//</sub> and ends with the end of line. As with the existing comment, no token should be returned.</li>

 <li>The definition for the identifiers should be modified so that underscores can be included, however, consecutive underscores, leading and trailing underscores should not be permitted.</li>

 <li>A real literal token should be added. It should begin with a sequence of one or more digits following by a decimal point followed by zero or more additional digits. It may optionally end with an exponent. If present, the exponent should begin with an <sub>e</sub> or <sub>E</sub>, followed by an optional plus or minus sign followed by one or more digits. The token should be named <sub>REAL_LITERAL</sub>.</li>

 <li>A Boolean literal token should be added. It should have two lexemes, which are <sub>true</sub> and false. The token should be named <sub>BOOL_LITERAL</sub>.</li>

</ol>

You must also modify the header file <sub>tokens.h</sub> to include each the new tokens mentioned above.

The compilation listing generator code should be modified as follows:

<ol>

 <li>The <sub>lastLine</sub> function should be modified to compute the total number of errors. If any errors occurred the number of lexical, syntactic and semantic errors should be displayed.</li>

</ol>

If no errors occurred, it should display <sub>Compiled Successfully</sub>. It should return the total number of errors.

<ol start="2">

 <li>The <sub>appendError</sub> function should be modified to count the number of lexical, syntactic and semantic errors. The error message passed to it should be added to a queue of messages that occurred on that line.</li>

 <li>The <sub>displayErrors</sub> function should be modified to display all the error messages that have occurred on the previous line and then clear the queue of messages.</li>

</ol>

An example of the output of a program with no lexical errors is shown below:

1  (* Program with no errors *)

2

<ul>

 <li>function test1 returns boolean;</li>

 <li>begin</li>

 <li>7 + 2 &gt; 6 and 8 = 5 * (7 – 4);</li>

 <li>end;</li>

</ul>




Compiled Successfully

Here is the required output for a program that contains more than one lexical error on the same line:

1  — Function with two lexical errors

2

<ul>

 <li>function test2 returns integer;</li>

 <li>begin</li>

 <li>7 $ 2 ^ (2 + 4);</li>

</ul>

Lexical Error, Invalid Character $

Lexical Error, Invalid Character ^

<ul>

 <li>end;</li>

</ul>




Lexical Errors 2

Syntax Errors 0

Semantic Errors 0

You are to submit two files.

<ol>

 <li>The first is a <sub>.zip</sub> file that contains all the source code for the project. The <sub>.zip</sub> file should contain the flex input file, which should be a <sub>.l</sub> file, all <sub>.cc</sub> and <sub>.h</sub> files and a makefile that builds the project.</li>

 <li>The second is a Word document (PDF or RTF is also acceptable) that contains the documentation for the project, which should include the following:

  <ol>

   <li>A discussion of how you approached the project</li>

   <li>A test plan that includes test cases that you have created indicating what aspects of the program each one is testing and a screen shot of your compiler run on that test case</li>

   <li>A discussion of lessons learned from the project and any improvements that could be made</li>

  </ol></li>

</ol>


