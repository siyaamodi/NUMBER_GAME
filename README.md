# NUMBER_GAME
import java.util.Random;
import java.util.Scanner;

public class NUMBER_GAME {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        int score = 0;
        boolean playAgain = true;

        while (playAgain) {
            int targetNumber = random.nextInt(100) + 1;
            int maxAttempts = 5;
            int attempts = 0;

            System.out.println("Welcome to the Random Number Game!");
            System.out.println("I have generated a number between 1 and 100.");
            System.out.println("You have " + maxAttempts + " attempts to guess it.");

            while (attempts < maxAttempts) {
                System.out.println("Enter your guess (1-100):");
                int guess = scanner.nextInt();
                attempts++;

                if (guess == targetNumber) {
                    System.out.println("Congratulations! Your guess is correct!");
                    score++;
                    break;
                } else if (guess < targetNumber) {
                    System.out.println("Too low! Try again.");
                } else {
                    System.out.println("Too high! Try again.");
                }
            }

            if (attempts == maxAttempts) {
                System.out.println("Game over! You couldn't guess the number. The correct number was: " + targetNumber);
            }

            System.out.println("Your score is: " + score);
            System.out.println("Do you want to play again? (yes/no)");
            String playAgainInput = scanner.next();

            if (!playAgainInput.equalsIgnoreCase("yes")) {
                playAgain = false;
            }
        }

        System.out.println("Thank you for playing! Goodbye!");
        scanner.close();
    }
}
