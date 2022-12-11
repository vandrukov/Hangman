import random
import string
scope = string.ascii_lowercase
list_of_input = []
action = ""
actions = ["play", "results", "exit"]
won = 0
lost = 0
list_words = ["python", "java", "swift", "javascript"]
word = random.choice(list_words)
hint = list("-" * len(word))
letter = ""
attempts = 8
char = set(word)
word_list = list(word)

def results():
    global won
    global lost
    print(f"You won: {won} times")
    print(f"You lost: {lost} times")
    menu()    
    
def reset_values():
    global list_of_input
    global word
    global hint
    global letter
    global attempts
    global char
    global word_list
    list_of_input = []
    word = random.choice(list_words)
    hint = list("-" * len(word))
    letter = ""
    attempts = 8
    char = set(word)
    word_list = list(word)
    

def check_letter():
    global word
    global letter
    global hint
    global word_list
    global char
    global attempts
    global list_of_input
    global won
    if len(str(letter)) != 1:
        print("Please, input a single letter.")
        ask_letter()
    elif len(letter) != 1:
        print("Please, input a single letter.")
        ask_letter()
    elif letter not in scope:
        print("Please, enter a lowercase letter from the English alphabet.")
        ask_letter()
    else:
        if letter in char:
            list_of_input.append(letter)
            char.remove(letter)
            for i in range(0, len(word_list)):
                if word_list[i] == letter:
                    hint[i] = word_list[i]
            if "".join(hint) == word:
                won += 1
                print(f"You guessed the word {word}!")
                print("You survived!")
                menu()
            ask_letter()
        elif letter in list_of_input:
            print("You've already guessed this letter.")
            ask_letter()
        else:
            attempts -= 1
            print("That letter doesn't appear in the word.")
            list_of_input.append(letter)
            ask_letter()

def ask_letter():
    global attempts
    global hint
    global letter
    global lost
    print()
    print("".join(hint))
    if attempts == 0:
        print()
        lost += 1
        print("You lost!")
        menu()
    elif "".join(hint) == word:
        menu()
    else: 
        letter = input("Input a letter: ")
        check_letter()

def play(): 
    global attempts
    global letter
    reset_values()
    while attempts != 0:
        letter = ask_letter()
        check_letter()

def menu():
    global action
    global actions
    while action not in actions:
        action = input('Type "play" to play the game, "results" to show the scoreboard, and "exit" to quit:')
    if action == "play":
        action = ""
        play()
    elif action == "results":
        action = ""
        results()
    elif action == "exit":
       quit() 

print("H A N G M A N")
menu()
