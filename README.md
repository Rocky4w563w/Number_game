# Number_game.java
import java.util.Random;
import java.util.Scanner;

public class SimpleNumberGame {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        Random random = new Random();
        int number = random.nextInt(100) + 1; // Random number from 1 to 100
        int guess;
        int attempts = 0;
        int maxAttempts = 7;

        System.out.println("Guess the number between 1 and 100. You have " + maxAttempts + " attempts.");

        while (attempts < maxAttempts) {
            System.out.print("Enter your guess: ");
            guess = input.nextInt();
            attempts++;

            if (guess == number) {
                System.out.println("Correct! You guessed the number in " + attempts + " attempts.");
                break;
            } else if (guess < number) {
                System.out.println("Too low.");
            } else {
                System.out.println("Too high.");
            }

            if (attempts == maxAttempts) {
                System.out.println("You've used all attempts. The number was: " + number);
            }
        }

        input.close();
    }
}
