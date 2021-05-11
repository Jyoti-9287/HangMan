# HangMan
import random
 
l=["Python", "Java", "Computer","Learning","Tutorial"]
word=random.choice(l)
gusses=[]
done=False
allowed_errors=7
while not done:
    for letter in word:
        if letter.lower() in gusses:
            print(letter, end=" ")
        else:
            print("_" , end=" ")
    print("\n")
    guess=input("Allowed Errors left {allowed_errors}, Next guess: ")
    gusses.append(guess.lower())
    if guess.lower() not in word.lower():
        allowed_errors-=1
        if allowed_errors==0:
            break
    done=True
    for letter in word:
        if letter.lower() not in gusses:
            done=False
if done:
    print(f"You found the word! It was {word}")
else:
    print(f"Game Over! The word was {word}")
