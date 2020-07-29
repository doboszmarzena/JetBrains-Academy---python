# JetBrains-Academy---python
1. First project: 
Zookeeper
Description
It's time to make your project more convenient and understandable. In this final stage, your software will be ready for use by the zoo staff. Your program should understand the habitat numbers, show the animals, and be able to work infinitely.

Objectives
These are your tasks at this point:

Your program should repeat the behavior from the previous stage, now in a loop.
Do not forget to add an exit opportunity for the program: inputting the word exit must terminate the program.
At the end of execution, it must print See you!.

2. Second project:
Coffee Machine
About
What can be better than a cup of coffee during a break? A coffee that you don’t have to make yourself. It’s enough to press a couple of buttons on the machine and you get a cup of energy; but first, we should teach the machine how to do it. In this project, you will work on programming a coffee machine simulator. The machine works with typical products: coffee, milk, sugar, and plastic cups; if it runs out of something, it shows a notification. You can get three types of coffee: espresso, cappuccino, and latte. Since nothing’s for free, it also collects the money.

Description
Let's redesign our program and write a class that represents the coffee machine. The class should have a method that takes a string as input. Every time the user inputs a string to the console, the program invokes this method with one argument: the line that user input to the console. This system simulates pretty accurately how real-world electronic devices work. External components (like buttons on the coffee machine or tapping on the screen) generate events that pass into the single interface of the program.

The class should not use system input at all; it will only handle the input that comes to it via this method and its string argument.

The first problem that comes to mind: how to write that method in a way that it represents all that coffee machine can do? If the user inputs a single number, how can the method determine what that number is: a variant of coffee chosen by the user or the number of the disposable cups that a special worker added into the coffee machine?

The right solution to this problem is to store the current state of the machine. The coffee machine has several states it can be in. For example, the state could be "choosing an action" or "choosing a type of coffee". Every time the user inputs something and a program passes that line to the method, the program determines how to interpret this line using the information about the current state. After processing this line, the state of the coffee machine can be changed or can stay the same.

Objective
Your final task is to refactor the program. Make it so that you can communicate with the coffee machine through a single method. Good luck!

3. Third project: Simple Chatty Bot
Description
At the final stage, you will improve your simple bot so that it can give you a test and check your answers. The test should be a multiple-choice quiz about programming. Your bot has to repeat the test until you answer correctly and congratulate you upon completion.

Objective
Your bot can ask anything you want, but there are two rules for your output:
•	the line with the test should end with the question mark character;
•	an option starts with a digit followed by the dot (1., 2., 3., 4.)
If a user enters an incorrect answer, the bot may print a message:
Please, try again.
The program should stop on the correct answer and print Congratulations, have a nice day! at the end.

4. Fourth project -  Credit Calculator:
Description
Finally, let's add to our calculator the capacity to compute the differentiated payment. In such a kind of payment where the part for reducing the credit principal is constant. Another part of the payment is for interest repayment and it reduces during the credit term. It means that the payment is different each month. Let’s look at the formula:

As you can see, the user has to input a lot of parameters. So it might be convenient to use command-line arguments.

Suppose you used to run your credit calculator via command line like this:

python credit_calc.py
Using command-line arguments you can run your program this way:

python credit_calc.py --type=diff --principal=1000000 --periods=10 --interest=10
In that case, your program can get different values and not ask the user to input them. It can be useful when you are developing your program and trying to find a mistake and want to run the program with the same parameters again and again. Also, it's convenient if you made a mistake in a single parameter. You don't have to input all other values again.

To confidently work with command-line arguments in Python, check out a tutorial.

Objectives
At this stage, it is required to implement these features:

the calculation of differentiated payment. To do this, the user may run the program specifying interest, count of periods and credit principal.
a capacity to calculate the same values as in the previous stage for annuity payment (principal, count of periods and value of the payment). A user specifies all known parameters with command-line arguments, while a single parameter will be unknown. This is the value the user wants to calculate.

handling of invalid parameters. It's a good idea to show an error message Incorrect parameters in case of invalid parameters (they are discussed in detail below).

The final version of your program is supposed to work from the command line and parse the following parameters:

--type, which indicates the type of payments: "annuity" or "diff" (differentiated). If --type is specified neither as "annuity" nor as "diff", or it is not specified at all, show the error message.
> python credit_calc.py --principal=1000000 --periods=60 --interest=10
Incorrect parameters
--payment, that is a monthly payment. For --type=diff the payment is different each month, so we can't calculate periods or principal, therefore, its combination with --payment is invalid, too:
> python credit_calc.py --type=diff --principal=1000000 --interest=10 --payment=100000
Incorrect parameters
--principal is used for calculations of both types of payment. You can get its value knowing the interest, annuity payment and periods.
--periods parameter denotes the number of months and/or years needed to repay the credit. It's calculated based on the interest, annuity payment and principal.
--interest is specified without a percent sign. Note that it may accept a floating-point value. Our credit calculator can't calculate the interest, so these parameters are incorrect:
> python credit_calc.py --type=annuity --principal=100000 --payment=10400 --periods=8
Incorrect parameters
Let's make a comment. You might have noticed that for differentiated payments you will need 4 out of 5 parameters (excluding payment), and the same is true for annuity payments (missing either periods, payment or principal). Thus, when less than four parameters are given, you should display the error message too:

> python credit_calc.py --type=annuity --principal=1000000 --payment=104000
Incorrect parameters
Another case when you should output this message is negative values. We can't work with these!

> python credit_calc.py --type=diff --principal=30000 --periods=-14 --interest=10
Incorrect parameters
Finally, don't forget to compute the value of overpayment, and you'll have your real credit calculator!


5. Fifth project - Rock-Paper-Scissors:
Description
How about some brand new rules? The original game has a fairly small choice of options.
Extended versions of the game are decreasing the probability of draw, so it could be cool to play them.
Now, your program should be able to accept alternative lists of options, like Rock, Paper, Scissors, Lizard, Spock, or even a list like this:
At this stage, before the start of the game, the user will be able to choose the options that will be used. After entering his/her name, the user should provide a list of options separated by a comma. For example,

rock,paper,scissors,lizard,spock

If the user inputs an empty line, your program should start the game with default options: rock. paper and scissors.

After the game options are defined, your program should output Okay, let's start

Whatever list of options the user chooses, your program, obviously, should be able to identify which option beats which, that is, the relationships between different options. First, every option is equal to itself (causing a draw if both user and computer choose the same option). Secondly, every option wins over one half of the other options of the list and gets defeated by another half. How to determine which options are stronger or weaker than the option you're currently looking at? Well, you can try to do it this way: take the list of options (provided by the user or the default one). Find the option for which you want to know its relationships with other options. Take all the options that follow this chosen option in the list. Add to them the list of options that precede the chosen option. Now you have another list of options that doesn't include the "chosen" option and has the different order of elements in it (first go the options following the chosen one in the original list, after them are the ones that precede it). So, in this "new" list, the first half of the options will be defeating the "chosen" option, and the second half will get beaten by it.

For example, the user's list of options is rock,paper,scissors,lizard,spock. You want to know what options are weaker than lizard. By looking at the list spock,rock,paper,scissors you realize that spock and rock will be beating the lizard, and paper and scissors will get defeated by it. For spock it'll be almost the same, but it'll get beaten by rock and paper, and prevail over scissors and lizard. For the version of the game with 15 options, you can look at the picture above to understand the relationships between options.

Of course, this is not the most efficient way to determine which option prevails over which. You are welcome to try to develop some other methods of tackling this problem.

Objectives
Your program should:

a)Output a line Enter your name: . Note that the user should enter his/her name on the same line (not the one following the output!)
b) Read input specifying the user's name and output a new line Hello, <name>
c) Read a file named rating.txt and check if there's a record for the user with the same name; if yes, use the score specified in the rating.txt for this user as a starting point for calculating the score in the current game. If no, start counting user's score from 0.
d) Read input specifying the list of options that will be used for playing the game (options are separated by comma). If the input is an empty line, play with default options.
e) Output a line Okay, let's start
f) Play the game by the rules defined on the previous stages:
g) Read user's input
h) If the input is !exit, output Bye! and stop the game
i) If the input is the name of the option, then:
j) Pick a random option
k) Output a line with the result of the game in the following format (<option> is the name of the option chosen by the program):
Lose -> Sorry, but computer chose <option>
Draw -> There is a draw (<option>)
Win -> Well done. Computer chose <option> and failed
l) For each draw, add 50 points to the score. For each user's win, add 100 to his/her score. In case the user loses, don't change the score.
m) If the input corresponds to anything else, output Invalid input
n) Play the game again (with the same options that were defined before the start of the game)

