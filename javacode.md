import java.util.Scanner;

public class guessmaster{
    public static void guessingNumberGame()
    {
        Scanner sc = new Scanner(System.in);

        
        int number = 1 + (int)(100 * Math.random());
        
        
        int attempts = 0; 
        
        
        int K = 5; 
        boolean guessedCorrectly = false;

        System.out.println(
            "A number is chosen between 1 and 100.");
        System.out.println(
            "You have " + K
            + " attempts per round to guess the correct number.");

        while (!guessedCorrectly) {
            
    
            for (int i = 0; i < K; i++) {
                System.out.print("Enter your guess: ");
                int guess = sc.nextInt();
                attempts++; 

                if (guess == number) {
                    System.out.println(
                        "Congratulations! You guessed the correct number in "
                        + attempts + " attempts.");
                    guessedCorrectly = true;
                    break;
                }
                else if (guess < number) {
                    System.out.println(
                        "The number is greater than "
                        + guess);
                }
                else {
                    System.out.println(
                        "The number is less than " + guess);
                }
            }

            if (!guessedCorrectly) {
                
            
                System.out.println("You have used all " + K
                                   + " attempts.");
                System.out.print(
                    "Do you want to continue guessing? (yes/no): ");
                String response = sc.next();

                if (!response.equalsIgnoreCase("yes")) {
                    System.out.println(
                        "Game Over! The correct number was: "
                        + number);
                    break;
                }
            }
        }

        sc.close();
    }

    public static void main(String[] args)
    {
        guessingNumberGame();
    }
}
