import random

def print_header():
    print("---------------------------------------------------")
    print("              ROCK, PAPER, SCISSORS")
    print("---------------------------------------------------")

def get_user_choice():
    while True:
        print("\nChoose (R)ock, (P)aper, or (S)cissors:")
        choice = input(">").lower()
        if choice in ['r', 'rock']:
            return 'rock'
        elif choice in ['p', 'paper']:
            return 'paper'
        elif choice in ['s', 'scissors']:
            return 'scissors'
        elif choice == 'quit':
            print("Thanks for playing!")
            exit()
        else:
            print("Invalid choice. Please choose again.")

def get_computer_choice():
    return random.choice(['rock', 'paper', 'scissors'])

def print_choices(player_choice, computer_choice):
    print(f"\nYou chose: {player_choice}")
    print(f"Computer chose: {computer_choice}")

def determine_winner(player_choice, computer_choice):
    if player_choice == computer_choice:
        return "It's a tie!"
    elif (player_choice == 'rock' and computer_choice == 'scissors') or \
         (player_choice == 'paper' and computer_choice == 'rock') or \
         (player_choice == 'scissors' and computer_choice == 'paper'):
        return "You win!"
    else:
        return "Computer wins!"

def play_game():
    while True:
        print_header()
        player_choice = get_user_choice()
        computer_choice = get_computer_choice()

        print_choices(player_choice, computer_choice)

        result = determine_winner(player_choice, computer_choice)
        print(result)

        play_again = input("\nDo you want to play again? (yes/no): ").lower()
        if play_again != 'yes':
            print("Thanks for playing!")
            break

if __name__ == "__main__":
    play_game()

