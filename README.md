# JetBrains-Academy---python
**My projects:**

 1. **Zookeeper**
 2. **Coffee Machine**
 3. **Simple Chatty Bot**
 4. **Credit Calculator**
 5. **Rock-Paper-Scissors**
 6. **Hangman**
 7. **Tic-Tac-Toe**
 8. **Dominoes**
 9. **Currency Converter**
 10. **Arithmetic Exam Application**
 11. **Generating Randomnes**
 12. **The Simple Banking System**


## 1. Zookeeper

**Description**
It's time to make your project more convenient and understandable. In this final stage, your software will be ready for use by the zoo staff. Your program should understand the habitat numbers, show the animals, and be able to work infinitely.

**Objectives**
These are your tasks at this point:
Your program should repeat the behavior from the previous stage, now in a loop.
Do not forget to add an exit opportunity for the program: inputting the word exit must terminate the program.
At the end of execution, it must print See you!

## 2. Coffee Machine
**About**
What can be better than a cup of coffee during a break? A coffee that you don’t have to make yourself. It’s enough to press a couple of buttons on the machine and you get a cup of energy; but first, we should teach the machine how to do it. In this project, you will work on programming a coffee machine simulator. The machine works with typical products: coffee, milk, sugar, and plastic cups; if it runs out of something, it shows a notification. You can get three types of coffee: espresso, cappuccino, and latte. Since nothing’s for free, it also collects the money.

**Description**
Let's redesign our program and write a class that represents the coffee machine. The class should have a method that takes a string as input. Every time the user inputs a string to the console, the program invokes this method with one argument: the line that user input to the console. This system simulates pretty accurately how real-world electronic devices work. External components (like buttons on the coffee machine or tapping on the screen) generate events that pass into the single interface of the program.

The class should not use system input at all; it will only handle the input that comes to it via this method and its string argument.

The first problem that comes to mind: how to write that method in a way that it represents all that coffee machine can do? If the user inputs a single number, how can the method determine what that number is: a variant of coffee chosen by the user or the number of the disposable cups that a special worker added into the coffee machine?

The right solution to this problem is to store the current state of the machine. The coffee machine has several states it can be in. For example, the state could be "choosing an action" or "choosing a type of coffee". Every time the user inputs something and a program passes that line to the method, the program determines how to interpret this line using the information about the current state. After processing this line, the state of the coffee machine can be changed or can stay the same.

**Objective**
Your final task is to refactor the program. Make it so that you can communicate with the coffee machine through a single method. Good luck!

## 3. Simple Chatty Bot

**Description**
At the final stage, you will improve your simple bot so that it can give you a test and check your answers. The test should be a multiple-choice quiz about programming. Your bot has to repeat the test until you answer correctly and congratulate you upon completion.

**Objective**
Your bot can ask anything you want, but there are two rules for your output:
•	the line with the test should end with the question mark character;
•	an option starts with a digit followed by the dot (1., 2., 3., 4.)
If a user enters an incorrect answer, the bot may print a message:
*Please, try again.*
The program should stop on the correct answer and print: *Congratulations, have a nice day*! at the end.

## 4. Credit Calculator:

**Description**
Finally, let's add to our calculator the capacity to compute the differentiated payment. In such a kind of payment where the part for reducing the credit principal is constant. Another part of the payment is for interest repayment and it reduces during the credit term. It means that the payment is different each month. 
As you can see, the user has to input a lot of parameters. So it might be convenient to use command-line arguments.
Suppose you used to run your credit calculator via command line like this:
python credit_calc.py
Using command-line arguments you can run your program this way:

python credit_calc.py --type=diff --principal=1000000 --periods=10 --interest=10
In that case, your program can get different values and not ask the user to input them. It can be useful when you are developing your program and trying to find a mistake and want to run the program with the same parameters again and again. Also, it's convenient if you made a mistake in a single parameter. You don't have to input all other values again.

To confidently work with command-line arguments in Python, check out a tutorial.

**Objectives**
At this stage, it is required to implement these features:

the calculation of differentiated payment. To do this, the user may run the program specifying interest, count of periods and credit principal.
a capacity to calculate the same values as in the previous stage for annuity payment (principal, count of periods and value of the payment). A user specifies all known parameters with command-line arguments, while a single parameter will be unknown. This is the value the user wants to calculate.

handling of invalid parameters. It's a good idea to show an error message Incorrect parameters in case of invalid parameters (they are discussed in detail below).

The final version of your program is supposed to work from the command line and parse the following parameters:

--type, which indicates the type of payments: "annuity" or "diff" (differentiated). If --type is specified neither as "annuity" nor as "diff", or it is not specified at all, show the error message.

python credit_calc.py --principal=1000000 --periods=60 --interest=10 Incorrect parameters    --payment, that is a monthly payment. For --type=diff the payment is different each month, so we can't calculate periods or principal,    therefore, its combination with --payment is invalid, too:
  python credit_calc.py --type=diff --principal=1000000 --interest=10 --payment=100000 Incorrect parameters    --principal is used for calculations of both types of payment. You can get its value knowing the interest, annuity payment and periods.    --periods parax

## 5. Rock-Paper-Scissors

**Description**

How about some brand new rules? The original game has a fairly small choice of options.

Extended versions of the game are decreasing the probability of draw, so it could be cool to play them.  
Now, your program should be able to accept alternative lists of options, like Rock, Paper, Scissors, Lizard, Spock, or even a list.
At this stage, before the start of the game, the user will be able to choose the options that will be used. After entering his/her name, the user should provide a list of options separated by a comma. For example,

`rock,paper,scissors,lizard,spock`

If the user inputs an empty line, your program should start the game with default options: rock. paper and scissors.

After the game options are defined, your program should output  `Okay, let's start`

Whatever list of options the user chooses, your program, obviously, should be able to identify which option beats which, that is, the relationships between different options. First, every option is equal to itself (causing a draw if both user and computer choose the same option). Secondly, every option wins over one half of the other options of the list and gets defeated by another half. How to determine which options are stronger or weaker than the option you're currently looking at? Well, you can try to do it this way: take the list of options (provided by the user or the default one). Find the option for which you want to know its relationships with other options. Take all the options that follow this chosen option in the list. Add to them the list of options that precede the chosen option. Now you have another list of options that doesn't include the "chosen" option and has the different order of elements in it (first go the options following the chosen one in the original list, after them are the ones that precede it). So, in this "new" list, the first half of the options will be defeating the "chosen" option, and the second half will get beaten by it.

For example, the user's list of options is  `rock,paper,scissors,lizard,spock`. You want to know what options are weaker than  `lizard`. By looking at the list  `spock,rock,paper,scissors`  you realize that  `spock` and  `rock` will be beating the  `lizard`, and  `paper` and  `scissors` will get defeated by it. For spock it'll be almost the same, but it'll get beaten by  `rock` and  `paper`, and prevail over  `scissors` and  `lizard`. For the version of the game with 15 options, you can look at the picture above to understand the relationships between options.

Of course, this is not the most efficient way to determine which option prevails over which. You are welcome to try to develop some other methods of tackling this problem.

**Objectives**

**Your program should:**

1.  Output a line  `Enter your name:` . Note that the user should enter his/her name on the same line (not the one following the output!)
2.  Read input specifying the user's name and output a new line  Hello, <name>
3.  Read a file named  `rating.txt`  and check if there's a record for the user with the same name; if yes, use the score specified in the  `rating.txt`  for this user as a starting point for calculating the score in the current game. If no, start counting user's score from 0.
4.  Read input specifying the list of options that will be used for playing the game (options are separated by comma). If the input is an empty line, play with default options.
5.  Output a line  `Okay, let's start`
6.  Play the game by the rules defined on the previous stages:
7.  Read user's input
8.  If the input is  `!exit`, output  `Bye!`  and stop the game
9.  If the input is the name of the option, then:
10.  Pick a random option
11.  Output a line with the result of the game in the following format (`<option>`  is the name of the option chosen by the program):
    -   Lose ->  `Sorry, but computer chose <option>`
    -   Draw ->  `There is a draw (<option>)`
    -   Win ->  `Well done. Computer chose <option> and failed`
12.  For each draw, add 50 points to the score. For each user's win, add 100 to his/her score. In case the user loses, don't change the score.
13.  If the input corresponds to anything else, output  `Invalid input`
14.  Play the game again (with the same options that were defined before the start of the game)


## 6. Hangman

**About**

Games can help you kill time when you’re bored. But before smartphones, people played games the classic way – with paper and pencil. Let’s recreate one such game and improve your programming skills in the process. In this project, you will code Hangman, a game where the player has to guess a word, letter by letter, in a limited number of attempts. Make a program that plays Hangman with you – and good luck with the guessing!

 **Learning outcomes**

Best project for Python Basics: uses functions, loops, lists, and other variables. The Random module is a cherry on top. Don’t be intimidated by the number of stages – they ensure that your immersion in Python is smooth and safe.

**Stage 1/8: Hello, Hangman!**
Welcome the user: print “The game will be available soon”.

**Stage 2/8: I want to play a game**

For starters, let’s give the player only one chance to guess the word. Learn and use “Input” and “if” to implement this stage.

**Stage 3/8: Make your choice**

Let’s make the game more challenging: now it will randomly choose one of four words from a list.

**Stage 4/8: Help is on the way**

Enable hints in your game: let it show the total length of the word or its first three letters. Slicing will help you implement this part.

**Stage 5/8: Keep trying**

Use a loop to extend the number of attempts to eight. Now we’re talking!

**Stage 6/8: The value of life**

The outcome of the game may be fatal, which makes the game all the more exciting. Implement this feature so that players don’t lose strikes when they guess a letter right. The While loop will help.

**Stage 7/8: Error!**

Improve the game by handling different error cases. Repeating a letter, entering too many characters, or using non-Latin characters shouldn’t cost your player a strike.

**Stage 8/8: Menu, please**

While a dinner starts with the menu, our project ends with one. Create a menu for your game so that players can replay it or exit.

## 7. Tic-Tac-Toe

##### About

Everybody remembers this paper-and-pencil game from childhood: Tic-Tac-Toe, also known as Noughts and crosses or Xs and Os. A single mistake usually costs you the game, but thankfully it is simple enough that most players discover the best strategy quickly. Let’s program Tic-Tac-Toe and get playing!

##### Learning outcomes

After finishing this project, you'll get to know a lot about planning and developing a complex program from scratch, using functions, handling errors, and processing user input.

**Stage 1/5: Welcome to the battlefield!**
To start things off, the program needs to be able to print any state of the field. You’ll write a serious multi-line program using a lot of prints.

**Stage 2/5: The user is the gamemaster**
Now it’s time to analyze user input and print the state of the field depending on it. You’ll learn to address specific positions in a string to achieve the required outcome.

**Stage 3/5: What's up on the field?**
Now we’re going to write a fully-functioning multi-line program that responds to the user’s actions and analyzes the state of the field. Not only will it tell you who is winning, but it will also determine if the situation on a given field is theoretically possible!

**Stage 4/5: First move!**
Tic-tac-toe is not all about analysis – a game is meant to be played! Write a program that can change the state of the field, as your first real step toward a fully-functioning game application!

**Stage 5/5: Fight!**
Finally! Thanks to this app, you can always challenge a friend to play a quick game of Tic-Tac-Toe!:
**Description**
We are at the finish line! But playing alone is not so interesting, is it? Let's combine our successes in past stages and get Tic-Tac-Toe with the ability to play from the beginning (empty field) to the result (win or draw).
Now it is time to make a working game!
In the last stage, make it so you can play a full game with a friend. First one of you moves as X, and then the other one moves as O.

**Objectives**
In this stage, you should write a program that:

1.  Prints an empty field at the beginning of the game.
2.  Creates a game loop where the program asks the user to enter the cell coordinates, analyzes the move for correctness and shows a field with the changes if everything is ok.
3.  Ends the game when someone wins or there is a draw.

You need to output the final result after the end of the game.

## 8. Dominoes

##### About
Have you ever wanted to code a game where the computer is your enemy? Well, this little project allows you to do just that.
Take turns playing classic dominoes against your computer in a race to victory.
Learn, how artificial intelligence can make use of simple statistics to make educated decisions. This project is all about basic concepts, put them to practice by making a fun little game.

##### Learning outcomes
This project is all about basic concepts. You'll work with strings, tuples, lists, conditional statements, and more.
 

 ## 9. Currency Converter

##### About
Want to convert one currency to another? You can go to your bank website and do the math by yourself. Or you can write a program to do it quickly and efficiently! The Currency Converter is a simple console program that calculates the amount of money you get by converting one currency to another.

##### Learning outcomes
You will learn many concepts of Python — basic types, variables, arithmetic operations, loops, and working with files. Get a taste of more advanced features — JSON format, caching, and how to work with the network. You will write a currency converter program that uses a third-party service.
 
**What you’ll do and what you’ll learn**
**Stage 1/6 Write a simple program that greets a new type of cryptocurrency.**
 **Stage 2/6 All of a sudden you have found a stash of crypto tokens. Write a program that calculates the number of dollars received from their sale.**
**Stage 3/6 Read the number of conicoins, exchange rate, and a currency code as the user input. Calculate what you will receive.**
**Stage 4/6 Find out how much you get in five other currencies after selling your conicoins.**
**Stage 5/6 Print the actual exchange rates for USD and EUR using a 3rd party service.**
**Stage 6/6 Pick two currencies and find their actual exchange rates. Learn how to use cache to store the information about hundreds of currencies.**
 
 
 ## 10. Arithmetic Exam Application

##### About
Many people are fond of interactive learning. In this project, you will learn how to write an application that can facilitate solving arithmetic operations in a quick manner. The application will generate a mathematical expression for a user to solve. Implement various levels of difficulty and let the application save the results and show the progress of learning.

##### Learning outcomes
Learn how to handle input and output, employ the random number generator, and write the output to a file.
 
**What you’ll do and what you’ll learn**
**Stage 1/6 Write a mini calculator to work with numbers and simple mathematical operations..**
 **Stage 2/6 Use the random number generator to make your tasks random.**
**Stage 3/6 Test with one question is boring, let's add more questions! Also, we need to find a way to handle user typos..**
**Stage 4/6 Solving mathematical expressions is helpful, but many students prefer to get marks. Let's add marks and save the results!.**
 
 
 ## 11. Generating Randomnes
#### About
Everyone knows that people are bad at generating random things. In this project, we will check this assumption using a small program that will predict "random" user actions. We'll see if you can beat it!
 
#### Learning outcomes
In addition to raising the metaphysical question of free will, this project will teach you to work with dictionaries and lists, as well as with simple predictive models.
 
**What you’ll do and what you’ll learn**
1. **Stage 1/4 Teach your program to remember user input and filter out inappropriate symbols..**
2. **Stage 2/4 Write a module that will form a “user profile” based on the data collected in the previous stage.**
3. **Stage 3/4 Create a predictor that will guess the user's next input based on their previous keypresses. We will also validate the performance of this predictor.**
4. **Stage 4/4 Now we are ready to try to beat our own system in pressing random keys. Try to be as unpredictable as you can!**
 
 
 ## 12. The Simple Banking System
 #### About
 You have created the foundation of our banking system. Now let's take the opportunity to deposit money into an account, make transfers and close an account if necessary.
Now your menu should look like this:

1. **Balance**
2. **Add income**
3. **Do transfer**
4. **Close account**
5. **Log out**
0. **Exit**
 
If the user asks for Balance, you should read the balance of the account from the database and output it into the console.

Add income item should allow us to deposit money to the account.

Do transfer item should allow transferring money to another account. You should handle the following errors:

1. If the user tries to transfer more money than he/she has, output: Not enough money!
2. If the user tries to transfer money to the same account, output the following message: You can't transfer money to the same account!
3. If the receiver's card number doesn’t pass the Luhn algorithm, you should output: Probably you made a mistake in the card number. Please try again!
4. If the receiver's card number doesn’t exist, you should output: Such a card does not exist.
5. If there is no error, ask the user how much money they want to transfer and make the transaction.
6. If the user chooses the Close account item, you should delete that account from the database.

Do not forget to commit your DB changes right after executing a query!
 
 
