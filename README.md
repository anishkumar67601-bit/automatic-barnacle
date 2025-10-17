
# automatic-barnacle
🎮 No one here to play this game, I just trying enjoy!

import random

choices = ["stone", "paper", "scissors"]

def get_user_choice():
    user_input = input("Enter your choice (stone/paper/scissors): ").lower()
    if user_input not in choices:
        print("Invalid choice, please try again.")
        return get_user_choice()
    return user_input

def get_computer_choice():
    return random.choice(choices)

def determine_winner(user, computer):
    if user == computer:
        return "It's a tie!"
    elif (user == "stone" and computer == "scissors") or \
         (user == "scissors" and computer == "paper") or \
         (user == "paper" and computer == "stone"):
        return "You win!"
    else:
        return "Computer wins!"

def play():
    user_choice = get_user_choice()
    computer_choice = get_computer_choice()
    print(f"Computer chose: {computer_choice}")
    print(determine_winner(user_choice, computer_choice))

if __name__ == "__main__":
    play()