---
title: Task - Animal Quiz
weight: 25
---
![Animal Quiz](https://1.bp.blogspot.com/-DQMVWo9T7lU/XnYaibyvymI/AAAAAAAAADM/aeUahrwfJcUKx9VtYbOJRh2dIM1UZORwACLcBGAsYHQ/s640/external-content.duckduckgo.com2.jpeg)

Are you a fan of quizzes? Would you like to make one yourself? In this project, you’ll build an animal quiz. Even though the questions are about animals, this project can be easily modified to be about any other topic.

In this example, you'll see bits of code with annotations. The code in black is new code to be added. The code in grey is existing code; use this to work out where to add the new lines of code. The instructions will ask you to run the code at various points. Make sure you do this and that the code successfully runs. **Do not proceed to the next step until the previous one works. You'll just make things harder for yourself!**

{{< columns >}}
## What happens 
The program asks the player some questions about animals. They get three chances to answer each question—you don’t want to make the quiz too difficult! Each correct answer will score one point. At the end of the quiz, the program reveals the player’s final score.

## How it works 
This project makes use of a function—a block of code with a name that performs a specific task. A function lets you use the same code repeatedly, without having to type it all in every time. Python has lots of built-in functions, but it also lets you create functions of your own.
<--->
![Flow chart](https://1.bp.blogspot.com/-VvT1l1fqhZo/XnYd1e_0BAI/AAAAAAAAADY/4_8NYpLRsQMObSDNPVYqHnLv0rbmCm0FACLcBGAsYHQ/s1600/21.03.2020_19.19.49_REC.png)
{{< /columns >}}
 
## Putting it together
It’s now time to build your quiz! First you’ll create the questions and the mechanism for checking the answers. Then you’ll add the code that gives the player three attempts to answer each question.

## 1. Create A New File
Open Mu Editor. Make sure the editor is in the right mode. Click the **Mode** button in the top left, and choose **Python 3**. Create a new file, and save it with the name `animalQuiz.py` in your Digital Tech folder, in a folder named `quiz`.
 
{{< columns >}}
## 2.Create the score variable 
Type in the code shown here to create a variable called `score` and set its starting value to `0`.

## 3.Introduce the game
Next, create a message to introduce the game to the player. This will be the first thing that the player sees on the screen.

## 4.Run the code
Now try running the code. Press the Run button from the bar at the top. What happens next? You should see the welcome message in the interactive panel at the bottom of the window. Press the Stop button (where the Run button was) to stop the program and return to editing.
<--->
![](https://1.bp.blogspot.com/-u0FGizCrSSI/XnYeG8ukw6I/AAAAAAAAAEQ/ra16kYrkwT8B93nlCxcnVXI7s6VE8A2xACEwYBhgL/s400/21.03.2020_19.20.49_REC.png)
{{< /columns >}}

{{< columns >}}
## 5.Ask a question (user input) 
The next line of code asks a question and waits for the player’s response. The answer (the user input) is saved in the variable `guess1`. Run the code to make sure the question appears.
<--->
![](https://1.bp.blogspot.com/-gHvjUmQIGug/XnYeLoGjFwI/AAAAAAAAAEk/PQpGl2uVEc4whtMXIR8OQi_3ZI6Ui8CtACEwYBhgL/s400/21.03.2020_19.21.38_REC.png)
{{< /columns >}}

{{< columns >}}
## 6.Build a check function 
The next task is to check if the player’s guess is correct. Type this code at the top of your script, before `score = 0`. The code creates a function, called `check_guess()`, that will check if the player’s guess matches the correct answer. The two words in brackets are **[parameters]({{< ref "/glossary/parameter" >}})**—bits of information the function needs. When you call (run) a function, you assign (give) values, known as **[arguments]({{< ref "/glossary/argument" >}})**, to its parameters.
<--->
![](https://1.bp.blogspot.com/-kxNri3ZHAt4/XnYeLthCLNI/AAAAAAAAAEc/v6fuEfU59rkIqyBN-WX41hjtzDxtLby6wCEwYBhgL/s400/21.03.2020_19.22.05_REC.png)
{{< /columns >}}

{{< columns >}}
## 7.Call the function 
Now add a line at the end of the script to call (run) the check_guess() function. This code tells the function to use the player’s guess as the first parameter and the phrase “polar bear” as the second parameter.
<--->
![](https://1.bp.blogspot.com/-vHQ5aqwFHKI/XnYeMiZsogI/AAAAAAAAAEg/p-VRgNhy7z8LEby-7yJZpBuU7qw003jAwCEwYBhgL/s400/21.03.2020_19.22.28_REC.png)
{{< /columns >}}

{{< columns >}}
## 8.Test the code 
Try running the code again and type in the correct answer. The shell window should look like this.
<--->
![](https://1.bp.blogspot.com/-UIxNAa5jeUs/XnhNC9Km5oI/AAAAAAAAAFA/REsnzvIKBEw3okdU8H83teUfG0t-llAzACLcBGAsYHQ/s400/21.03.2020_19.22.46_REC.png)
{{< /columns >}}

{{< columns >}}
## 9.Add some more questions
It takes more than one question to make a quiz! Add two more questions to the program, following the same steps as before. We’ll store the player’s answers in the variables `guess2` and `guess3`.
<--->
![](https://1.bp.blogspot.com/-9EFib5HhC0w/XnhNDaKI76I/AAAAAAAAAFE/OXqcDkv3GpALu-8wxyd2gPddnc0FRlofQCEwYBhgL/s400/21.03.2020_19.23.13_REC.png)
{{< /columns >}}

{{< columns >}}
## 10.Display the score
The next line of code will reveal the player’s score in a message when the quiz ends. Add it to the bottom of the file, under the last question.
<--->
![](https://1.bp.blogspot.com/-QSzIl8P8D1g/XnhNDXUR-dI/AAAAAAAAAFQ/7EVs0tIsp14dEffUaaOfuaihWoHcL7z3wCEwYBhgL/s400/21.03.2020_19.27.13_REC.png)
{{< /columns >}}

{{< columns >}}
## 11. Ignore case
What happens if the player types “Lion” instead of “lion”? Will they still get a point? No, the code will tell them it’s the wrong answer! To fix this, you need to make your code smarter. Python has a `lower()` function, which changes words into all lower-case characters. In your code, replace `if guess == answer:` with the line shown on the right in bold.
<--->
![](https://1.bp.blogspot.com/-Hw4yRDsg_bE/XnhNDiDhRPI/AAAAAAAAAFs/Nu-t1M83tG098CXw7uDYKUWS5p8QGQxGwCEwYBhgL/s400/21.03.2020_19.27.54_REC.png)
{{< /columns >}}

{{< columns >}}
## 12. Test the code again
Run your code for a third time. Try typing the correct answers using a mixture of capitals and lower-case letters and see what happens.
<--->
![](https://1.bp.blogspot.com/-bAMz9PNZq6o/XnhOmyszKfI/AAAAAAAAAF0/YmP6FTRjg8IeVz64W_ZYPFB4f1XsMKBzwCLcBGAsYHQ/s400/21.03.2020_19.18.13_REC.png)
{{< /columns >}}
