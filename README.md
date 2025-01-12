# Rock-paper-sessior-in-java
Rock-paper-scissors can be used to study decision-making and human behavior.
Rock-Paper-Scissors in Java
 * Core Idea:
   * A game where two players choose one of three options: Rock, Paper, or Scissors.
   * Rock beats Scissors.
   * Scissors beats Paper.
   * Paper beats Rock.
   * If both players choose the same, it's a draw.
 * Java Implementation:
   * Use an enum to represent the choices: ROCK, PAPER, SCISSORS.
   * Write logic to compare player choices and determine the winner.
   * Get player input and display the result.
In essence, it involves:
 * Representing choices: Using an enum for clear and organized code.
 * Determining winner: Implementing rules like "Rock beats Scissors" in Java code.
 * Getting player input: Allowing players to enter their choices (e.g., using Scanner).
 * Displaying results: Showing the winner or a draw to the players.
This provides a basic understanding of how to implement Rock-Paper-Scissors in Java.

import java.util.Random;
import java.util.Scanner;

public class Main {
    public static void main(String[] args){

        // ROCK PAPER SCISSORS GAME

        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        String[] choices = {"rock", "paper", "scissors"};
        String playerChoice;
        String computerChoice;
        String playAgain = "yes";

        do{
            System.out.print("Enter your move (rock, paper, scissors): ");
            playerChoice = scanner.nextLine().toLowerCase();

            if(!playerChoice.equals("rock") && !playerChoice.equals("paper") && !playerChoice.equals("scissors")){
                System.out.println("Invalid choice");
                continue;
            }

            computerChoice = choices[random.nextInt(3)];
            System.out.println("Computer choice: " + computerChoice);

            if(playerChoice.equals(computerChoice)){
                System.out.println("It's a tie!");
            }
            else if((playerChoice.equals("rock") && computerChoice.equals("scissors")) ||
                       (playerChoice.equals("paper") && computerChoice.equals("rock")) ||
                       (playerChoice.equals("scissors") && computerChoice.equals("paper"))){
                System.out.println("You win!");
            }
            else{
                System.out.println("You lose!");
            }

            System.out.print("Play again (yes/no): ");
            playAgain = scanner.nextLine().toLowerCase();

        }while(playAgain.equals("yes"));

        System.out.println("Thanks for playing!");

        scanner.close();
    }
}
