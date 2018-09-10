# Python-mini-projects
Python practice 

41)
Write a method that takes input as a string (of many words) and
#returns a list of unique words in lowercase. (Do not use Sets for now!).
#Conditions -
#Remove the comma(,) and dots(.) from the words.
#Ex - ‘Tree’ ‘Tree,’ and ‘Tree.’ are not three different words but just 1 unique word.
#Unique words can be of any case, i.e., ‘Tree’ and ‘tree’ are the same word
#Given an input string as -
# “Simple is better than complex, Complex is better than complicated.”,
#Solution should return -
#['simple', 'is', 'better', 'than', 'complex', 'complicated']
#HINT - Explore the string library for split() and strip() methods..!
def unique_words(line):
    lower_line = line.lower()
    x = lower_line.strip(".")
  
    y = x.replace(",","")
    z = y.split()
  
    unique = list(set(z))
    print (unique)
            
    




40)
# E. not_bad
# Given a string, find the first appearance of the
# substring 'not' and 'bad'. If the 'bad' follows
# the 'not', replace the whole 'not'...'bad' substring
# with 'good'.
# Return the resulting string.
# So 'This dinner is not that bad!' yields:
# This dinner is good!
def not_bad(a):
    bad_index = a.find('bad')
    not_index = a.find('not')
    
    if bad_index > not_index:
        print (a.replace(a[(not_index):(bad_index+3)],'good'))
    else:
        print(a)

not_bad('this dinner is not that bad')

Result: this dinner is good









39)
F. front_back
Consider dividing a string into two halves.
If the length is even, the front and back halves are the same length.
If the length is odd, we'll say that the extra char goes in the front half.
e.g. 'abcde', the front half is 'abc', the back half 'de'.
Given 2 strings, a and b, return a string of the form
a-front + b-front + a-back + b-back


def front_back(a,b):
    if len(a) % 2 == 0:
        a_front = a[:((len(a))//2)]
        a_back = a[((len(a))//2):]
    else:
        a_front = a[:((len(a)//2)+1)]
        a_back = a[((len(a))//2+1):]
                      
  
    
    
    if len(b) % 2 == 0:
        b_front = b[:((len(b))//2)]
        b_back = b[((len(b))//2):]
    else:
        b_front = b[:((len(b)//2)+1)]
        b_back = b[((len(b))//2+1):]
                      
  
                      
    print(a_front+b_front+a_back+b_back)
   KitDontenut

   

front_back('Kitten', 'Donut')
Result = 



38)
# Additional basic string exercises
# D. verbing
# Given a string, if its length is at least 3,
# add 'ing' to its end.
# Unless it already ends in 'ing', in which case
# add 'ly' instead.
# If the string length is less than 3, leave it unchanged.
# Return the resulting string.
def verbing(s):
    if len(s) >= 3 and s[-3:] != 'ing':
        s = s + 'ing'
    elif len(s) >= 3 and s[-3:] == 'ing':
        s = s + 'ly'
    
    return s
        
        





37)

# D. MixUp
# Given strings a and b, return a single string with a and b separated
# by a space '<a> <b>', except swap the first 2 chars of each string.
# e.g.
#   'mix', pod' -> 'pox mid'
#   'dog', 'dinner' -> 'dig donner'
# Assume a and b are length 2 or more.
def mix_up(a, b):
    y = a.replace(a[0],b[0])
    y = a.replace(a[1],b[1])
    z = b.replace(b[0],a[0])
    z = b.replace(b[1],a[1])
    return y + ' ' + z


mix_up(‘dig’, ‘donner’)



36)
def fix_start(s):
    print(s.replace(s[0], '*'))
   
fix_start(‘babble’)







35)
def both_ends(s):
    if len(s) >= 2:
            return s[:2] + s[-2:]
    else:
            return ''
    

    both_ends(‘spring’)






34)
def donuts(count):
    if count <=5:
        print("number of donuts:") + print(count)
    else:
        print("number of donuts: Many")








32)
use filter to return the word from a list of words which starts with a target letter

def word_list(wordlist,letter):
    desired_words = filter(lambda word:word[0] == letter, wordlist)
    return desired_word
33)
use zip and list comprehension to return a list of the same length where each value is the two strings from L1 and L2 concatenated together with connector between them

def concatenate(L1,L2,connector):
    return[word1+connector+word2 for (word1,word2) in zip(L1,L2)]



31)
Use reduce to take a list of digits and return the number that they correspond to. Do not convert to strings

def digits_to_num(digits):
    x = len(digits)
    answer = 0
    for numbers in digits:
            answer = numbers *( 10**x) + answer
            x = x - 1
    return answer

30)
def count_word(a):
    c = 0
    for i in a:
        c = c + 1
    return c

word_lengths = "how long are the words in this phrase"

w_lengths = list(map(count_word, word_lengths.split()))

print(w_lengths)



29)

Return the number of times names occur as a substring in a string ( if first and last letter of the string is same)

def name_in_strings(a):
    num = 0
    for i in range(0,(len(a)-2)):
        for j in range(i+1,(len(a)-1)):
                   if a[i] == a[j]:
                       num = num + 1
    print(num)
                   




28):
Define a function which can generate and print a tuple where the value are squares of numbers between 1 and 20

def gen_tup():
    x =[]
    for i in range(1,21):
        x = x+ [i**2]
    z = tuple(x)
    print(z)


27):
Take a string and print if the number in the string if there is any

def int_in_words(a):
    y = a.split()
    for i in y:
        if i.isdigit() == True:
            print(i)
        else:
            print("no numbers")
            

26)
Change return 

import math
def change_return():
    n = float(input("what is the cost ? "))
    y = float(input("what is the amount of money given ? "))
    
    change = float(y - n)  
    
    if change >= 0.25: 
        quarters = int(change // 0.25)
        z = change - quarters(0.25)
        if z >= 0.10: 
            dimes = z // 0.10
            f = z -dimes(0.10)
            if f >= 0.05:
                nickels = f//0.05
                x = f - nickels(0.05)
                if x >= 0.01:
                    pennies = x//0.01
        print("Number of quarters is {}, Number of dimes is {}, Number of nickels is {}, Number of Pennies is {}". format
          (quarters,dimes,nickels,dimes))
    
    elif change >= 0.10:
        dimes = change // 0.10
        f = change -dimes(0.10)
        if f >= 0.05:
            nickels = f//0.05
            x = f - nickels(0.05)
            if x >= 0.01:
                pennies = x//0.01
        print("Number of dimes is {}, Number of nickels is {}, Number of Pennies is {}". format
          (quarters,dimes,nickels,dimes))
                
    elif change >= 0.05:
        nickels = change//0.05
        x = f - nickels(0.05)
        if x >= 0.01:
            pennies = x//0.01
        print("Number of quarters is {}, Number of dimes is {}, Number of nickels is {}, Number of Pennies is {}". format
          (quarters,dimes,nickels,dimes))
                
    elif change >= 0.01:
        pennies = change//0.01
        print("Number of quarters is {}, Number of dimes is {}, Number of nickels is {}, Number of Pennies is {}". format(quarters,dimes,nickels,dimes))
        
    else: 
        print("no change")
25)
Mortgage Calculator - Calculate the monthly payments of a fixed term mortgage over given Nth terms at a given interest rate. Also figure out how long it will take the user to pay back the loan. For added complexity, add an option for users to select the compounding interval (Monthly, Weekly, Daily, Continually).



def mortgage_calculator():
    r = input("what is your interest rate in percent ? ")
    n = input("what is your fixed term mortgage ?")
    P = input(" How much did you buy your house for ?")
    z = input(" How many months are you paying the mortgagefor ?")
    n = input("How often it is compunded ?")
    interest_on_principal = float(P) * (float(r)/100)
    already_paid_of = int(z) * (float(P)/(int(z)*12))
    
    mortgage_money = float(P) + float(interest_on_principal) - float(already_paid_of)
    if lowercase(n) == monthly:
        
        
    print("you owe {} $ in mortgage money towards your home".format(mortgage_money))
    
24)
Find Cost of Tile to Cover W x H Floor - Calculate the total cost of tile it would take to cover a floor plan of width and height, using a cost entered by the user.

def cost_of_tile():
    n = int(input("what is the width of the floor in inches? "))
    y = int(input("what is the length of the floor in inches ? "))
    z = int(input("what is the cost of the tile in $ ? "))

    total_cost = n* y * z
    print("your total cost is {} $ ".format(total_cost))
3)
Prime factorization:

Have the user enter a number and find all the prime factors.



22)
All factors till a number

def prime_factors(n):
    x = [1]
    i = 2
    if n == 1:
        print(x)
    else:
        while i <= n:
            if n % i == 0:
                x = x + [i]
                i = i+1
            else:
                i = i+1
        
    print(x)

20)

Fibonacci sequence

def fibonacci_sequence(n):
    if n == 1:
        x = [1]
    elif n == 2:
        x =[1,1]
    else:
        x=[1,1]
        while n > 2:
            a = x[len(x)-1]
            b = x[len(x)-2]
            y = a + b
            x = x +[y]
            n = n-1
            continue
    print (x)

16:
BLACKJACK: Given three integers between 1 and 11, if their sum is less than or equal to 21, return their sum. If their sum exceeds 21 and there's an eleven, reduce the total sum by 10. Finally, if the sum (even after adjustment) exceeds 21, return 'BUST'

def blackjack(a,b,c):
    x = a+b+c
    if x <=21:
        return x
    elif x > 21 and (a == 11 or b ==11 or c ==11):
        return x -10 
    elif x > 21:
        print('BUST')

15
PAPER DOLL: Given a string, return a string where for every character in the original there are three characters
paper_doll('Hello') --> 'HHHeeellllllooo'



def paper_doll(a):
    x =''
    for i in range(0,len(a)):
        x = x+ a[i]*3
    print(x)
       
14

Given a list of ints, return True if the array contains a 3 next to a 3 somewhere.
has_33([1, 3, 3]) → True
has_33([1, 3, 1, 3]) → False
has_33([3, 1, 3]) → False

    

def has_33(a):
    for i in range(0,(len(a)-1)):
        if a[i]==a[i+1] == 3:
            return True
    return False

  13:


ALMOST THERE: Given an integer n, return True if n is within 10 of either 100 or 200
almost_there(90) --> True
almost_there(104) --> True
almost_there(150) --> False
almost_there(209) --> True
def almost_there(n):
    if n <= 110 and n >=90 or n <=210 and n >=190:
        return True
    else:
        return False        
12:
MASTER YODA: Given a sentence, return a sentence with the words reversed
master_yoda('I am home') --> 'home am I'
master_yoda('We are ready') --> 'ready are We'
def master_yoda(a):
    x = a.split()
    str = ''
    str = ' '.join(x[::-1])
    print(str) 
11:
OLD MACDONALD: Write a function that capitalizes the first and fourth letters of a name
old_macdonald('macdonald') --> MacDonald



def old_macdonald(a):
    print(a[0].capitalize()+a[1:3]+a[3].capitalize()+a[4:])

    
10:
MAKES TWENTY: Given two integers, return True if the sum of the integers is 20 or if one of the integers is 20. If not, return False
makes_twenty(20,10) --> True
makes_twenty(12,8) --> True
makes_twenty(2,3) --> False
def makes_twenty(a,b):
    if a == 20 or b ==20 or a+b == 20:
        return True
    else:
        return False
9:
ANIMAL CRACKERS: Write a function takes a two-word string and returns True if both words begin with same letter

def animal_crackers(str1):
    x = str1.split()
    if x[0][0]==x[1][0]:
        return True
    else:
        return False

8: LESSER OF TWO EVENS: Write a function that returns the lesser of two given numbers if both numbers are even, but returns the greater if one or both numbers are odd

def lesser_two_evens(a,b):
    if a % 2 == 0 and b % 2 ==0:
        if a < b:
            return a
        else:
            return b
    else:
        if a < b:
            return b
        else:
            return a

7:

write a program that picks a random integer from 1 to 100, and has players guess the number. The rules are:
If a player's guess is less than 1 or greater than 100, say "OUT OF BOUNDS"
On a player's first turn, if their guess is
within 10 of the number, return "WARM!"
further than 10 away from the number, return "COLD!"
On all subsequent turns, if a guess is
closer to the number than the previous guess return "WARMER!"
farther from the number than the previous guess, return "COLDER!"
When the player's guess equals the number, tell them they've guessed correctly and how many guesses it took!



from random import *
print("WELCOME TO GUESS ME!")
print("I'm thinking of a number between 1 and 100")
print("If your guess is more than 10 away from my number, I'll tell you you're COLD")
print("If your guess is within 10 of my number, I'll tell you you're WARM")
print("If your guess is farther than your most recent guess, I'll say you're getting COLDER")
print("If your guess is closer than your most recent guess, I'll say you're getting WARMER")
print("LET'S PLAY!")

x = randint(1,100)
num = 1
print(x)

y = input("input a number")
    if y < 1 or y > 100:
        print("out of bounds")
    elif y <= x+ 10 or y >= x-10:
        print("warm")
    elif y> x+10:
        print("cold")
    elif x == y;
        print("just one try")
    
    while true: 
        n = input("input a number")
        num = num+1
        if n < abs(x-y)
            print("warmer")
        elif n > abs(x+y):
            print("colder")
        elif n == x:
        print ( "num")
        return false

Online solution:

import random

num = random.randint(1,100)
print("WELCOME TO GUESS ME!")
print("I'm thinking of a number between 1 and 100")
print("If your guess is more than 10 away from my number, I'll tell you you're COLD")
print("If your guess is within 10 of my number, I'll tell you you're WARM")
print("If your guess is farther than your most recent guess, I'll say you're getting COLDER")
print("If your guess is closer than your most recent guess, I'll say you're getting WARMER")
print("LET'S PLAY!")
guesses = [0]
    
while True:

    # we can copy the code from above to take an input
    guess = int(input("I'm thinking of a number between 1 and 100.\n  What is your guess? "))
    
    if guess < 1 or guess > 100:
        print('OUT OF BOUNDS! Please try again: ')
        continue
    
    # here we compare the player's guess to our number
    if guess == num:
        print(f'CONGRATULATIONS, YOU GUESSED IT IN ONLY {len(guesses)} GUESSES!!')
        break
        
    # if guess is incorrect, add guess to the list
    guesses.append(guess)
    
    # when testing the first guess, guesses[-2]==0, which evaluates to False
    # and brings us down to the second section
    
    if guesses[-2]:  
        if abs(num-guess) < abs(num-guesses[-2]):
            print('WARMER!')
        else:
            print('COLDER!')
   
    else:
        if abs(num-guess) <= 10:
            print('WARM!')
        else:
            print('COLD!')

6:

Use a List Comprehension to create a list of the first letters of every word in the string below:

st = 'Create a list of the first letters of every word in this string'

[x[0] for x in st.split()]


5:
Write a program that prints the integers from 1 to 100. But for multiples of three print "Fizz" instead of the number, and for the multiples of five print "Buzz". For numbers which are multiples of both three and five print "FizzBuzz".

for x in range(1,101):
    if x % 3 == 0 and x % 5 == 0:
        print('fizzbuzz')
    
    elif x % 3 == 0:
        print('Fizz')
    
    elif x % 5 == 0:
        print('Buzz')
    else:
        print(x)

4:
st = 'Print every word in this sentence that has an even number of letters'
x = st.split()
for word in st.split():
    if len(word) % 2 == 0:
        print(word)

3:


Use a List Comprehension to create a list of all numbers between 1 and 50 that are divisible by 3.
 [x for x in range(0,50) if x % 3 == 0]

2:

Use range() to print all the even numbers from 0 to 10.

for i in range(0,10):
    if i % 2 ==0:
        print(i)



     1: 
st = 'Print only the words that start with s in this sentence'

for word in st.split():
    if word[0] == 's':
        print(word)











 
        















        

