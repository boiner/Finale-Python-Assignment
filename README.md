# Finale-Python-Assignment
>>> import random
>>> import json
>>> class Dice:
... def __init__(self, sides=6):
... self.sides = sides
... def roll(self):
... """Simulate rolling the dice."""
... return random.randint(1, self.sides)
...
>>> def save_roll_history(history, filename="roll_history.json"):
... with open(filename, "w") as file:
... json.dump(history, file)
... print(f"Roll history saved to {filename}.")
...
>>> def load_roll_history(filename="roll_history.json"):
... try:
... with open(filename, "r") as file:
... return json.load(file)
... except FileNotFoundError:
... print(f"No existing roll history found. Starting fresh.")
... return []
...
>>> def dice_rolling_simulator():
... print("Welcome to the Dice Rolling Simulator!")
... dice = Dice()
... roll_history = load_roll_history()
... while True:
... print("\nOptions:")
... print("1. Roll the dice")
... print("2. View roll history")
... print("3. Save and exit")
... choice = input("Enter your choice (1/2/3): ").strip()
... if choice == "1":
... result = dice.roll()
... print(f"You rolled a {result}!")
... roll_history.append(result)
... elif choice == "2":
... if roll_history:
... print("Roll History:", roll_history)
... else:
... print("No rolls yet!")
... elif choice == "3":
... save_roll_history(roll_history)
... print("Goodbye!")
... break
... else:
... print("Invalid choice. Please try again.")
...
>>> if __name__ == "__main__":
... dice_rolling_simulator()
...
Welcome to the Dice Rolling Simulator!
No existing roll history found. Starting fresh.

Options:
1. Roll the dice
2. View roll history
3. Save and exit
Enter your choice (1/2/3):

Options:
1. Roll the dice
2. View roll history
3. Save and exit
Enter your choice (1/2/3): 1
You rolled a 2!
