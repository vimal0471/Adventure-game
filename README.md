# Adventure-game
import java.util.Scanner;

public class AdventureGame {
    private static Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        startGame();
    }

    private static void startGame() {
        System.out.println("Welcome to the Adventure Game!");
        System.out.println("You are standing at the entrance of a dark cave.");
        System.out.println("You can see two paths in front of you. One leads to the left and the other to the right.");
        System.out.println("Which path do you want to choose? (type 'left' or 'right')");

        String choice = scanner.nextLine().trim().toLowerCase();

        if (choice.equals("left")) {
            goLeft();
        } else if (choice.equals("right")) {
            goRight();
        } else {
            System.out.println("Invalid input. Please try again.");
            startGame();
        }
    }

    private static void goLeft() {
        System.out.println("You have chosen the left path.");
        System.out.println("As you walk, you notice that the cave is getting darker and darker.");
        System.out.println("Suddenly, you hear a loud noise behind you.");
        System.out.println("Do you want to investigate the noise or keep moving forward? (type 'investigate' or 'forward')");

        String choice = scanner.nextLine().trim().toLowerCase();

        if (choice.equals("investigate")) {
            investigateNoise();
        } else if (choice.equals("forward")) {
            moveForward();
        } else {
            System.out.println("Invalid input. Please try again.");
            goLeft();
        }
    }

    private static void goRight() {
        System.out.println("You have chosen the right path.");
        System.out.println("As you walk, you notice that the cave is getting brighter and brighter.");
        System.out.println("Suddenly, you see a treasure chest in front of you.");
        System.out.println("Do you want to open the chest or keep moving forward? (type 'open' or 'forward')");

        String choice = scanner.nextLine().trim().toLowerCase();

        if (choice.equals("open")) {
            openChest();
        } else if (choice.equals("forward")) {
            moveForward();
        } else {
            System.out.println("Invalid input. Please try again.");
            goRight();
        }
    }

    private static void investigateNoise() {
        System.out.println("You investigate the noise and find a hidden door.");
        System.out.println("Do you want to open the door or go back? (type 'open' or 'back')");

        String choice = scanner.nextLine().trim().toLowerCase();

        if (choice.equals("open")) {
            openDoor();
        } else if (choice.equals("back")) {
            goLeft();
        } else {
            System.out.println("Invalid input. Please try again.");
            investigateNoise();
        }
    }

    private static void moveForward() {
        System.out.println("You keep moving forward and find a way out of the cave.");
        System.out.println("Congratulations, you have won the game!");
        System.exit(0);
    }

    private static void openChest() {
        System.out.println("You open the chest and find a treasure inside.");
        System.out.println("Congratulations, you have won the game!");
        System.exit(0);
    }

    private static void openDoor() {
        System.out.println("You open the door and find a dragon inside.");
        System.out.println("The dragon eats you. Game over.");
        System.exit(0);
    }
}
