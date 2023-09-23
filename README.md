# HangmanGame
//my first game
/*
 * In this Hangman game, the player needs to guess a word randomly selected from a predefined list. They have a maximum number of tries (in this case, 6), and they guess one letter at a time. If they guess all the letters correctly before running out of tries, they win.
Feel free to replace the simple Hangman ASCII art with something more appealing if you wish. This is a basic implementation, and you can expand and enhance it as you like.





import java.util.Scanner;

public class Myfirstgame 

{
   private static final String[] WORDS = {"programming", "java", "hangman", "computer", "algorithm"};
   
   private static final int MAX_TRIES = 6;
   
   public static void main(String[] args)
   {
   Scanner scanner = new Scanner(System.in);
   
   String wordToGuess = getRandomWord();
   
   char[] guessedWord = new char[wordToGuess.length()];
   
   int tries = 0;
   
   boolean gameOver = false;
   for (int i = 0; i < wordToGuess.length(); i++) {
	            guessedWord[i] = '_';
 }

	        System.out.println("Welcome to Hangman!");
	        while (!gameOver) {
	            displayHangman(tries);
	            displayGuessedWord(guessedWord);
	            System.out.print("Enter a letter: ");
	            char guess = scanner.next().charAt(0);

	            if (wordToGuess.indexOf(guess) == -1) {
	                tries++;
	            } else {
	                for (int i = 0; i < wordToGuess.length(); i++) {
	                    if (wordToGuess.charAt(i) == guess) {
	                        guessedWord[i] = guess;
	                    }
	                }
	            }

	            if (tries == MAX_TRIES) {
	                gameOver = true;
	                System.out.println("You ran out of tries! The word was: " + wordToGuess);
	            }

	            if (wordToGuess.equals(String.valueOf(guessedWord))) {
	                gameOver = true;
	                System.out.println("Congratulations! You guessed the word: " + wordToGuess);
	            }
	        }

	        scanner.close();
	    }

	    private static String getRandomWord() {
	        return WORDS[(int) (Math.random() * WORDS.length)];
	    }

	    private static void displayHangman(int tries) {
	        // Display Hangman ASCII art based on the number of tries
	        // You can find Hangman ASCII art online and replace this part
	        System.out.println("Tries: " + tries);
	    }

	    private static void displayGuessedWord(char[] guessedWord) {
	        System.out.println("Word: " + new String(guessedWord));
	    }
	

}
