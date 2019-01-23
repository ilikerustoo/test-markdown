# Reflection by Mohammad Khan

## Describe the challenges associated with automatically testing this Python program

Compute_tf_monolith is monolith program which is a single large block of script instead of segregated functions and documentation to explain the different aspects of the program and why it does what it does. This made isolating parts of the program difficult and possibly being unable to be tested. The for loop for example, does not contain any documentation or comments explaining how exactly the text file is parsed through and why exactly are there certain frequency increments to which I deduced duplicate words are not ignored but in fact contribute to the counter. This is important to know as it affects the overall functionality or usefulness of the program.

## Describe your approach to automatically testing this Python program

Despite not needing to use pytest in this particular practical, I decided learning how to use this test suite would prove useful for future assignments and serve as an introduction to automated testing. I imported the "os" library to use the pipenv command to run the program along with the input file. In my case this looked like: `os.system("pipenv run python src/termfrequency/compute_tf_monolith.py inputs/input.txt")`. This served as one function known as `f()` and was tested with another function (test_f(capfd)) that used `capfd` which allowed access to stdout/stderr output created during test execution for an easy comparison with an assertion or expected output.

## Explain a programming style that would make it easier to test this program

The use of functions or methods would make compute_tf_monolith easier to understand as monolith programs are generally undesired and functions would be able to segregate the code into known parts responsible for known features/functions that can be easily identified, isolated, and tested. For example, the monolith program could have contained a function to read the file in and another function to actually parse through the words and this would allow to to performing test for if a file is opened or all or what conditions must be met within the file that is inputted and if duplicate words are counted or not.

Better documentation within this code would explain what each line does especially if the programmer
prefers to keep his or her work as one monolithic script file. Explaining each part lets us know what exactly can go wrong and what or how something can be tested instead of simply testing for an output every time. An important part of testing goes beyond looking for the ideal output especially on one's own machine and documentation clarifies what could be tested for full proof code that works under different conditions and multiple environments. Ideally these practices will allow us to better use pytest once we learn more about testing suites and automated testing.

## Explain the challenges that you encountered and how you overcame them

My was first problem was the actual approach to the testing and what exactly to test as this is my first time attempting to figuring out what formal, automated testing involves. In this case, the output of the compute_tf_monolith.py needed to verified to an exact expected output as there is only one output that could shown provided the program nor input.txt file is altered. I decided to use pytest which involved a slight learning curve since I have never used a test suite before. This was my second problem. Not knowing what pytest was capable of made me think about how exactly would compare the outputs. Eventually I learned about the `capfd` fixure to capture output but I ran into yet another problem - formatting. In asserting my output within pytest, I needed to careful in writing the exact output that was expected. Although this sounds trivial, I spent about 30 minutes to learn that I had accidentally not included another space that I needed to.

