#MOTION CUT PROJECT 
#HANGMAN GAME

import random

CATEGORIES = {
    'Animals': ['elephant', 'giraffe', 'monkey', 'penguin', 'zebra'],
    'Countries': ['canada', 'brazil', 'japan', 'india', 'australia'],
    'Movies': ['inception', 'avatar', 'titanic', 'fighter', 'matrix']
}
HANGMAN_PICS = [
    '''
    +---+
        |
        |
        |
        |
        |
    ========
    ''',
    '''
    +---+
    O   |
        |
        |
        |
        |
    ========
    ''',
    '''
    +---+
    O   |
    |   |
        |
        |
        |
    ========
    ''',
    '''
    +---+
    O   |
   /|   |
        |
        |
        |
    ========
    ''',
    '''
    +---+
    O   |
   /|\\  |
        |
        |
        |
    ========
    ''',
    '''
    +---+
    O   |
   /|\\  |
   /    |
        |
        |
    ========
    ''',
    '''
    +---+
    O   |
   /|\\  |
   / \\  |
        |
        |
    ========
    '''
]

def choose_word(category):
    return random.choice(CATEGORIES.get(category, []))

def display_word(word, guessed_letters):
    return ' '.join(letter if letter in guessed_letters else '_' for letter in word)

def hangman():
    category = input("Choose a category (Animals, Countries, Movies): ").capitalize()
    word_to_guess = choose_word(category)

    incorrect_guesses = 0
    max_incorrect_guesses = len(HANGMAN_PICS) - 1
    guessed_letters = set()

    print("Welcome to Hangman!")
    print(display_word(word_to_guess, guessed_letters))

    while incorrect_guesses < max_incorrect_guesses:
        guess = input("Guess a letter: ").lower()

        if guess in guessed_letters:
            print("You already guessed that letter. Try again.")
            continue

        guessed_letters.add(guess)

        if guess not in word_to_guess:
            incorrect_guesses += 1
            print(HANGMAN_PICS[incorrect_guesses])

        print(display_word(word_to_guess, guessed_letters))

        if all(letter in guessed_letters for letter in word_to_guess):
            print("Congratulations! You guessed the word:", word_to_guess)
            break

    else:
        print("Sorry, you ran out of guesses. The word was:", word_to_guess)

if __name__ == "__main__":
    hangman()
