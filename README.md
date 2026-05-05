# Number-gussing-game
import random
print("Welcome to the Number Guessing Game!")
print("Choose difficulty level:")
print("1. Easy (10 attempts)")
print("2. Medium (7 attempts)")
print("3. Hard (5 attempts)")
choice = input("Enter 1, 2, or 3: ")
if choice == "1":
    attempts = 10
elif choice == "2":
    attempts = 7
elif choice == "3":
    attempts = 5
else:
    print("Invalid choice. Defaulting to Medium.")
    attempts = 7
secret_number = random.randint(1, 100)
print("\nI'm thinking of a number between 1 and 100.")
for i in range(attempts):
    try:
        guess = int(input(f"\nAttempt {i+1}/{attempts} - Enter your guess: "))
    except ValueError:
        print("Please enter a valid number!")
        continue
    if guess < secret_number:
        print("Too low!")
    elif guess > secret_number:
        print("Too high!")
    else:
        print("Congratulations! You guessed it!")
        break
else:
    print("\nYou've used all attempts.")
    print("The correct number was:", secret_number)

