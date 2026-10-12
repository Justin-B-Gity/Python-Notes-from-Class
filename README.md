# Python-Notes-from-Class
These are the problems that I had done in class, to help me learn python 

Chapter 1

Chapter 1-1

Chapter 1-2




Chapter 1-3

# Write your code here
base = float(input("Enter the base: "))
height = float(input("Enter the height: "))
area = .5 * base * height 
print(f"The area is {area} square units.")

Chapter 1-4

# Write your code here
radius = float(input("Enter the radius: "))
area = 3.14 * radius **2
print(f"The area is {area} square units.")

Chapter 1-5

# Write your program here
height = float(input("Enter the height: "))
width = float(input("Enter the width: "))
depth = float(input("Enter the depth: "))
volume = height * width * depth
print(f"The volume is {volume} cubic units.")






Chapter 2

Chapter 2-1

Chapter 2-2

# Write your program here
edges = int(input("Enter the cube's edge: "))
surface_area = 6*edges**2
print(f"The surface area is {float(surface_area)} square units.")

Chapter 2-3

# Write your program here

OLDIES = 2.00
NEW_VIDEOS = 3.00

new_vids = int(input("Enter the number of new videos: "))
old_vids = int(input("Enter the number of oldies: "))

total = float((OLDIES*old_vids) + (NEW_VIDEOS*new_vids))
print(f"The total cost is ${total}")

Chapter 2-4
# Write your program here
from math import pi

radius = float(input("Enter the sphere's radius: "))

diameter = radius * 2
print(f"Diameter: {diameter}")

circumference = 2 * pi * radius 
print(f"Circumference: {circumference}")

surface_area = 4 * pi * radius**2
print(f"Surface area: {surface_area}")

volume = (4/3) * pi * radius**3
print(f"Volume: {volume}")

Chapter 2-5 
# Write your program here
mass = float(input("Enter the object's mass: "))
velocity = float(input("Enter the objects's velocity: "))
momentum = mass * velocity
print(f"The object's momentum is {momentum}")


Chapter 3
Chapter 3-1

side1 = int(input("Enter the first side: "))
side2 = int(input("Enter the second side: "))
side3 = int(input("Enter the third side: "))

if side1 == side2 and side2 == side3:
    print("The triangle is equilateral.")
else:
    print("The triangle is not equilateral.")


Chapter 3-3
# Write your program here
# TKTK: Add started code here.

import math 

small_Num = int(input("Enter the smaller number: "))
large_Num = int(input("Enter the larger number: "))

count = 0
range_size = large_Num - small_Num + 1
guesses = math.ceil(math.log(range_size,2))
#print(guesses)

while count < guesses:
    #print(count)

    print(f"{small_Num} {large_Num}")
    num = (small_Num + large_Num)//2

    print(f"Your number is {num}")
    choice = input("Enter =, <, or >: ")

    if choice == "=":
        count += 1
        print(f"Hooray! I've got it in {count} tries!")
        break

    elif choice == "<":
        large_Num = num - 1 
        count += 1  

    elif choice == ">":
        small_Num = num + 1
        count += 1
    
    if (small_Num > large_Num) and count == guesses :
            print("I'm out of guesses, and you cheated!")
            break
    elif small_Num > large_Num:
            print("you cheated")
            break

else:
    print("I'm out of guesses!")

Chapter 3-4

ball_Drop = int(input("Enter the height from which the ball is dropped: ")) # 25
bounce_Index = float(input("Enter the bounciness index of the ball: ")) # 0.5
bounce_Num = int(input("Enter the number of times the ball is allowed to continue to bounce: ")) # 3

total = 0
count = 0
while count != bounce_Num:
    total += ball_Drop + (ball_Drop*bounce_Index)
    ball_Drop = ball_Drop * bounce_Index
    count += 1 

print(f"Total distance traveled is: {total} units.")#65.625

Chapter 3-5

# Write your program here
initial = int(input("Enter the intital number of organisms: "))
rate_of_Growth = float(input("Enter the rate of growth [a real number > 1]: "))
hours = int(input("Enter the number of hours to achieve the rate of growth: "))
total_Hours = int(input("Enter the total hours of growth: "))

count = 0
while count != total_Hours:
    initial *= rate_of_Growth
    count += hours
total = int(initial)

print(f"The total population is {total}")
    
    
Chapter 4
Chapter 4-1

plainText = input("Enter a message: ")
distance = int(input("Enter the distance value: "))
code = ""

for ch in plainText: 
    ordValue = ord(ch)
    cipherValue = ordValue + distance 
    if cipherValue > 127:
        cipherValue = distance - (127 - ordValue + 1)
    code += chr(cipherValue)
print(code)


Chapter 4-2

# Write your program here
code = input("Enter a message: ")
distance = int(input("Enter the distance value: "))
plainText = ""

for ch in code: 
    chrValue = ord(ch)
    cipherValue = chrValue - distance 
    if cipherValue > 127:
        cipherValue = distance - (127 - chrValue + 1)
    plainText += chr(cipherValue)
print(plainText)

Chapter 4-3

# Write your program here

infile = input("Enter the input file name: ")
outfile = input("Enter the output file name: ")
distance = int(input("Enter the distance value: "))

inputFile = open(infile,"r")
plainText = inputFile.read()
code = ""

outfile = open(outfile,"w")

for ch in plainText: 
    ordValue = ord(ch)
    cipherValue = ordValue + distance 
    if cipherValue > 127:
        cipherValue = distance - (127 - ordValue + 1)
    code += chr(cipherValue)
outfile.write(code)
outfile.close()


# Write your program here
infile = input("Enter the input file name: ")
outfile = input("Enter the output file name: ")
distance = int(input("Enter the distance value: "))

inputFile = open(infile,"r")
code = inputFile.read()

plainText = ""
outfile = open(outfile,"w")

for ch in code: 
    chrValue = ord(ch)
    cipherValue = chrValue - distance 
    if cipherValue > 127:
        cipherValue = distance - (127 - chrValue + 1)
    plainText += chr(cipherValue)
outfile.write(plainText)
outfile.close()

Chapter 4-4 

decimal = int(input("Enter a decimal integer: "))
octal = ""

if decimal == 0:
    print(decimal)
else:
    while decimal > 0:
        remainder = decimal % 8
        decimal //= 8
        octal = str(remainder) + octal

print(f"The octal representation is {octal}")

octal = input("Enter a string of octal digits: ")
decimal = 0
exponent = len(octal) - 1

if octal == 0:
    print(octal)
for num in octal:
    decimal = decimal + int(num) * 8 ** exponent
    exponent = exponent - 1

print(f"The integer value is {decimal}")


Chapter 4-5
# Write your program here
bits = input("Enter a string of bits: ")
if len(bits) > 1:
    bits = bits[-1] + bits[:-1]
#print(bits[1+1])
print(bits)

# Write your program here
bits = input("Enter a string of bits: ")
if len(bits) > 1:
    bits = bits[1:] + bits[0]
#print(bits[1+1])
print(bits)

Chapter 5
Chapter 5-1

def mean(lyst):
    average = 0
    for num in lyst:
        average += num
    if len(lyst) == 0:
       return 0
    return average / len(lyst)

def median(lyst):
    numbers = []
    for number in lyst:
        numbers.append(number)
    numbers.sort()
    if len(numbers) == 0:
        return 0
    else:
        midpoint = len(numbers) // 2
        if len(numbers) % 2 == 1:
            return numbers[midpoint]
        else: #elif midpoint % 2 == 0:
            return (numbers[midpoint] + numbers[midpoint - 1]) / 2

def mode(lyst):
    theDictionary = {}
    for number in lyst:
        if number not in theDictionary:
            theDictionary[number] = 1
        elif number in theDictionary:
            theDictionary[number] += 1

    if len(theDictionary) == 0:
        return 0
    else:
        max_Val = max(theDictionary.values())
        for key in theDictionary:
            if theDictionary[key] == max_Val:
                return key
def main():
    lyst = [8, 2, 5, 3, 9, 6, 2, 7]  #[3, 1, 7, 1, 4, 10] 1 1 3 4 7 10
    print(f"List {lyst}")
    print(f"Mode: {mode(lyst)}")
    print(f"Median: {median(lyst)}")
    print(f"Mean: {mean(lyst)}")

if __name__ == "__main__":
  main()


Chapter 5-2

# Write your program here
filename = input("Enter the file name: ")
count = 0
nList = []

f = open(filename,"r")
for line in f:
    count += 1
    nList += [line]
print(f"The file has {count} lines.")

while True:
    lineNum = int(input("Enter a line number [0 to quit]: "))
    if lineNum == 1:
        print(nList[0])
    elif lineNum > 1:
        print(nList[lineNum-1])
    elif lineNum == 0:
        break  

Chapter 5-3

import random

def getWords(fname):
    with open(fname,"r") as f:
        contentList = []
        for line in f:
            contentList += line.strip().split(" ")

    return tuple(contentList)

articles = getWords("articles.txt")
nouns = getWords("nouns.txt")
verbs =  getWords("verbs.txt")
prepositions = getWords("prepositions.txt")

Chapter 5-4

import random

def getWords(fname):
    with open(fname,"r") as f:
        contentList = []
        for line in f:
            contentList += line.strip().split(" ")

    return tuple(contentList)

articles = getWords("articles.txt")
nouns = getWords("nouns.txt")
verbs =  getWords("verbs.txt")
prepositions = getWords("prepositions.txt")
conjunction = getWords("conjunction.txt")
adjective = getWords("adjective.txt")

def prepositionalPhrase():
    """Builds and returns a prepositional phrase."""
    prep_Chance = random.choice([0,1])
    if prep_Chance: 
        return random.choice(prepositions) + " " + nounPhrase()
    else: 
        return nounPhrase()

Chapter 5-5

# Write your program here
lookUpTable = {"0":0, "1":1, "2":2, "3":3, 
               "4":4 ,"5":5, "6":6, "7":7,
               "8":8, "9":9 ,"A":10, "B": "11", 
               "C":12, "D":13, "E":14, "F":15}

def repToDecimal(string, base):
    decimal = 0
    if base == 2:
        position = len(string) - 1
        #print(position)
        for bit in string: 
            decimal += lookUpTable[bit] * 2**position
            position -= 1
        
    elif base == 8:
        position = len(string) - 1
        #print(position)
        for bit in string: 
            decimal += lookUpTable[bit] * 8**position
            position -= 1

    elif base == 16:
        position = len(string) - 1
        #print(position)
        for bit in string: 
            decimal += lookUpTable[bit] * 16**position
            position -= 1
    
    elif base == 10:
        position = len(string) - 1
        #print(position)
        for bit in string: 
            decimal += lookUpTable[bit] * 10**position
            position -= 1
    else:
        print("Enter correct base.")
    return decimal 
    
print(repToDecimal("10",10))


Chapter 6
Chapter 6-1

import math
# Write your code here
def newton(user):
    tolerance = 0.000001
    estimate = 1.0
    user = float(user)
    while True:
        estimate = (estimate + user/estimate) / 2
        difference = abs(user - estimate **2)
        if difference <= tolerance:
            break
    #print(estimate)
    #print(f"The program's estimate is {estimate}")
    #print(f"Python's estimate is {math.sqrt(float(user))}")
    #return f"The program's estimate is {x}"
    return estimate 


def main():
    while True:
        user = input("Enter a positive number or enter/return to quit: ")
        if user == "":
            break
        estimate = newton(user)
        
        print(f"The program's estimate is {estimate}")
        print(f"Python's estimate is {math.sqrt(float(user))}")

main()
Chapter 6-2

import math


# Write your code here
def newton(user):
    global tolerance 
    tolerance = 0.000001
    estimate = 1.0
    user = float(user)
    while True:
        estimate = improveEstimate(user,estimate)
        if limitReached(user, estimate):
            break
    #print(estimate)
    #print(f"The program's estimate is {estimate}")
    #print(f"Python's estimate is {math.sqrt(float(user))}")
    #return f"The program's estimate is {x}"
    return estimate 

def limitReached(user,estimate):
    # returns true if the estimate is within the tolerance or false otherwise.
    difference = abs(user - estimate **2)
    return difference <= tolerance
    
def improveEstimate(user,estimate):\
    # returns an improved estimate
    return (estimate + user/estimate) /2


def main():
    while True:
        user = input("Enter a positive number or enter/return to quit: ")
        if user == "":
            break
        x = float(user)
        
        print(f"The program's estimate is {newton(user)}")
        print(f"Python's estimate is      {math.sqrt(x)}")
main()

Chapter 6-3
# Write your code here
def isSorted(sList):
    for i in range(len(sList) - 1):
        if sList[i] > sList[i+1]:
            return False
    return True
         

Chapter 6-4
"""
File: recognizer.py
Programming Exercise 6.4
A grammar checker for sentences in a subset of English
defined by the following grammar rules:
sentence = nounphrase verbphrase [ and nounPhrase verbphrase ]
nounphrase = article [ adjective ] noun
verbphrase = verb nounphrase [ prepositionalphrase ]
Note that [] enclose an optional item.
The parts of speech are nouns, verbs, articles,
prepositions, adjectives, and conjunctions.
Inputs: purported sentences
Outputs: Ok, grammatically correct or
Not ok, grammatically incorrect
"""
articles = ("A", "THE")

nouns = ("BOY", "GIRL", "BAT", "BALL")

verbs = ("HIT", "SAW", "LIKED")

prepositions = ("WITH", "BY")

adjectives = ("RED", "LITTLE")

conjunctions = ("AND", "BUT")

# sentence = nounphrase verbphrase [ and nounPhrase verbphrase ]

def sentence(words):

  """Returns True if the words form
  a sentence, possibly with two independent
  clauses, or False otherwise."""
  isOk = nounPhrase(words) and verbPhrase(words)
  if len(words) > 0:
    conjunction = words.pop(0)
    return isOk and (conjunction in conjunctions) and \
        nounPhrase(words) and verbPhrase(words)
  else:
    return isOk

    
# nounphrase = article [ adjective ] noun

def nounPhrase(words):

  """Returns True if the first two words
  are an artyicle and a noun or the first three 
  words are an article, an adjective, and a noun,
  or False otherwise."""
  if len(words) < 2:
    return False

  else:
    article = words.pop(0)
    word = words.pop(0)
    if word in adjectives:
      if len(words) > 0:
        word = words.pop(0)
      else:
        return False
    return article in articles and word in nouns



# verbphrase = verb nounphrase [ prepositionalphrase ]

def verbPhrase(words):

  """Returns True if the words form
  a verb phrase with an optional prepositional
  phrase, or False otherwise."""
  if len(words) == 0:
    return False
  else:
    verb = words.pop(0)
    isOk = verb in verbs and nounPhrase(words)
    if len(words) > 0:
      if words[0] in prepositions:
        return isOk and prepositionalPhrase(words)
      else:
        return isOk
    else:
      return isOk


# prepositionalphrase = preposition nounphrase

def prepositionalPhrase(words):
  """Returns True if the words form
  a prepositional phrase or False otherwise."""
  if len(words) == 0:
    return False
  else:
    preposition = words.pop(0)
    return preposition in prepositions and nounPhrase(words)

def main():
  """Tests inputs for grammatical correctness until the
  user presses return."""
  while True:
    userInput = input("Enter a sentence or press return to quit: ")
    if userInput == "":
      return
    else:
      words = userInput.upper().split()
      if sentence(words):
        print("Ok, grammatically correct")
      else:
        print("Not ok, grammatically incorrect")
if __name__ == "__main__":
  main()

Chapter 6-5
# Write your code here

menu1 = ["Open", "Save", "Compile", "Run", "Quit"]
menu2 = ["Copy", "Cut", "Paste", "Quit"]

def main(menu):
    while True:
        printMenu(menu1)
        commandNumber = acceptCommand(len(menu))
        performCommand(commandNumber,menu)
        if commandNumber == len(menu):
            print("Have a nice day!")
            break

def printMenu(menu):
    # Prints the items in a menu, preceded by integers. 
    for number in range(len(menu)):
        print(number + 1, menu[number])

def acceptCommand(lengthOfMenu):
    # Inputs and returns a legitimate command number. 
    while True:
        command = int(input("Enter a number: "))
        if command < 1 or command > lengthOfMenu:
            print("Error: command not recognized")
        else:
            return command
        
def performCommand(commandNumber,menu):
    #selects and runs a command
    print(f"Command = {menu[commandNumber- 1 ]}")

if __name__ == "__main__":
    main(menu1)

Chapter 7

Chapter 7-1

import math
#Initialize the tolerance 
tolerance = 0.000001

def newton(user, estimate = 1):
    """returns the square root of x"""
    #Computes the difference and test for the base case
    difference = abs(user - estimate **2)
    if difference <= tolerance:
        return estimate
    else:
        return newton(user, (estimate + user/estimate) / 2)

def main():
    while True:
        user = input("Enter a positive number or enter/return to quit: ")
        if user == "":
            break
        user = float(user)
        
        print(f"The program's estimate is {newton(user)}")
        print(f"Python's estimate is      {math.sqrt(float(user))}")

main()

