import random

def get_random_word():
    wordlist = []
    with open("word.txt", 'r') as file:
        wordlist = file.read().split("\n")
    word = random.choice(wordlist)
    return word

def display_hangman(incorrect_guesses):
    stages = [
        """
           -----
           |   |
               |
               |
               |
               |
        --------
        """,
        """
           -----
           |   |
           O   |
               |
               |
               |
        --------
        """,
        """
           -----
           |   |
           O   |
           |   |
               |
               |
        --------
        """,
        """
           -----
           |   |
           O   |
          /|   |
               |
               |
        --------
        """,
        """
           -----
           |   |
           O   |
          /|\\  |
               |
               |
        --------
        """,
        """
           -----
           |   |
           O   |
          /|\\  |
          /    |
               |
        --------
        """,
        """
           -----
           |   |
           O   |
          /|\\  |
          / \\  |
               |
        --------
        """
    ]
    print(stages[incorrect_guesses])

def hangman():
    word = get_random_word()
    guessed_word = ['_'] * len(word)
    guessed_letters = set()
    incorrect_guesses = 0
    max_incorrect_guesses = 6

    print("Welcome to Hangman!")
    print("Guess the word:")
    print(' '.join(guessed_word))

    while incorrect_guesses < max_incorrect_guesses:
        guess = input("Enter a letter: ").lower()

        if len(guess) != 1 or not guess.isalpha():
            print("Invalid input. Please enter a single letter.")
            continue

        if guess in guessed_letters:
            print("You have already guessed that letter. Try again.")
            continue

        guessed_letters.add(guess)

        if guess in word:
            for i, letter in enumerate(word):
                if letter == guess:
                    guessed_word[i] = guess
            print("Good guess!")
        else:
            incorrect_guesses += 1
            print("Incorrect guess!")

        display_hangman(incorrect_guesses)
        print(' '.join(guessed_word))

        if '_' not in guessed_word:
            print("Congratulations! You guessed the word:", word)
            break
    else:
        print("You lost! The word was:", word)

if __name__ == "__main__":
    hangman()
