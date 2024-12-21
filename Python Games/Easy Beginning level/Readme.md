```python
import random

words = ["python", "java", "kotlin", "javascript"]
word_to_guess = random.choice(words)
chances = 7
guess_counter = 0
guessed_word = ["_"] * len(word_to_guess)

print("Welcome to the Word Guessing Game!")
print("You have 7 chances to guess the word.")
print(" ".join(guessed_word))

while guess_counter < chances:
    guess = input("Enter a letter: ").lower()
    guess_counter += 1

    if guess in word_to_guess:
        for index, letter in enumerate(word_to_guess):
            if letter == guess:
                guessed_word[index] = guess
        print("Good guess!")
    else:
        print("Wrong guess!")

    print(" ".join(guessed_word))

    if "_" not in guessed_word:
        print(f"Congratulations! You guessed the word '{word_to_guess}' in {guess_counter} attempts.")
        break
else:
    print(f"Sorry, you've used all your chances. The word was '{word_to_guess}'.")
```

### Explanation of the Loop Logic

1. **Initialization**:
   - A list of words is defined.
   - A random word is selected from the list using `random.choice`.
   - The number of chances is set to 7.
   - `guess_counter` is initialized to 0 to keep track of the number of guesses.
   - `guessed_word` is initialized as a list of underscores, representing the letters of the word to guess.

2. **Welcome Message**:
   - A welcome message is printed, along with the initial state of the guessed word.

3. **While Loop**:
   - The loop runs as long as `guess_counter` is less than `chances`.
   - The player is prompted to enter a letter.
   - `guess_counter` is incremented by 1 with each iteration.

4. **Checking the Guess**:
   - If the guessed letter is in the word to guess, the corresponding positions in `guessed_word` are updated.
   - A message indicating a good guess is printed.
   - If the guessed letter is not in the word, a message indicating a wrong guess is printed.

5. **Printing the Current State**:
   - The current state of the guessed word is printed.

6. **Winning Condition**:
   - If there are no underscores left in `guessed_word`, the player has guessed the word correctly, and a congratulatory message is printed. The loop is terminated using `break`.

7. **Losing Condition**:
   - If the loop completes without the player guessing the word, a message revealing the correct word is printed.

This loop logic ensures that the player has a limited number of attempts to guess the word, providing feedback after each guess and checking for win/loss conditions.
