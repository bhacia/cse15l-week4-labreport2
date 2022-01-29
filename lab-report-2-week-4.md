# Code Changes

1. Fixing code for when there's text between the brackets and parentheses.

![Image](https://bhacia.github.io/cse15l-week4-labreport2/md-parse-code-change-1.png)

2. Fixing code for when there's no end parenthesis.

![Image](https://bhacia.github.io/cse15l-week4-labreport2/md-parse-code-change-2.png)

3. Fixing code for when there's no brackets.

![Image](https://bhacia.github.io/cse15l-week4-labreport2/md-parse-code-change-3-pt1.png)
![Image](https://bhacia.github.io/cse15l-week4-labreport2/md-parse-code-change-3-pt2.png)

# Respective Test Files

1. Testing file with text between end bracket and open parenthesis: [test file 1](https://bhacia.github.io/markdown-parse/test-text-between-bracket-and-paren.md)

![Image](https://bhacia.github.io/cse15l-week4-labreport2/test-file-code-change-1.png)

2. Testing file with missing end parenthesis: [test file 2](https://bhacia.github.io/markdown-parse/test-missing-end-paren.md)

![Image](https://bhacia.github.io/cse15l-week4-labreport2/test-file-code-change-2.png)

3. Testing file with no brackets at all: [test file 3](https://bhacia.github.io/markdown-parse/test-file.md)

![Image](https://bhacia.github.io/cse15l-week4-labreport2/test-file-code-change-3.png)

# Original Symptoms of Failures

1. Content in test file 1 should not be treated as a link; output should be an empty arraylist: [OG test 1](https://bhacia.github.io/markdown-parse/ogTest1.md)

![Image](https://bhacia.github.io/cse15l-week4-labreport2/og-test-1-symptom-1.png)

Output is actually showing what's in the parentheses as a valid link.

2. Content in test file 2 should not throw an exception; output should be an empty arraylist: [OG test 2](https://bhacia.github.io/markdown-parse/ogTest2.md)

![Image](https://bhacia.github.io/cse15l-week4-labreport2/og-test-2-symptom-2.png)

Output is actually showing a String Index Out Of Bounds Exception.

3. Content in test file 3 should not be treated as a link; output should be an empty arraylist: [OG test 3](https://bhacia.github.io/markdown-parse/ogTest3.md)

![Image](https://bhacia.github.io/cse15l-week4-labreport2/og-test-3-symptom-3.png)

Output is actually showing what's in the parentheses as a valid link.

# Relationship Between the Bug, Symptom, and Failure-Inducing Input

1. The code doesn't take into consideration, what's a valid link or not. A valid link in markdown, doesn't contain text between the end bracket and open parenthesis. Although the code compiles and the test file showed no error, the output is still not we expect because we know that it's not a valid link. Therefore, we
attempted a fix by making the value of "openParen" equal to 1 + the value of "nextCloseBracket".

2. The code doesn't take into consideration, if there are missing parts of the link, in this case, the end parenthesis. A valid link in markdown contains both
open and close brackets **and** parentheses. Although the code compiles, the test file shows a String Index Out of Bounds Exception, since it's looking for that
end parenthesis. Therefore, we attempted a fix by writing an "if statement" at the beginning of the while loop to check if there actually is an end parenthesis.

3. The code doesn't take into consideration, if there are missing parts of the link, in this case, the open and close brackets. A valid link in markdown contains
both open and close brackets **and** parentheses. Although the code compiles and the test file showed no error, the output is still not we expect because we know
that it's not a valid link. Therefore, we attempted a fix by adding more "if statements" at the beginning of the while loop to check if there actually are
open and close brackets.
