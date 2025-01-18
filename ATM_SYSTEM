import java.util.Scanner;

class BankAccount {
    private double balance;

    public BankAccount(double initialBalance) {
        this.balance = initialBalance;
    }

    public double getBalance() {
        return balance;
    }

    public boolean withdraw(double amount) {
        if (amount > balance) {
            return false; // Insufficient funds
        } else {
            balance -= amount;
            return true;
        }
    }

    public void deposit(double amount) {
        balance += amount;
    }
}

class ATM {
    private BankAccount account;

    public ATM(BankAccount account) {
        this.account = account;
    }

    public void start() {
        Scanner scanner = new Scanner(System.in);
        boolean exit = false;

        System.out.println("Welcome to the ATM!");

        while (!exit) {
            System.out.println("\nPlease choose an option:");
            System.out.println("1. Withdraw");
            System.out.println("2. Deposit");
            System.out.println("3. Check Balance");
            System.out.println("4. Exit");

            System.out.print("Your choice: ");
            int choice = scanner.nextInt();

            switch (choice) {
                case 1: // Withdraw
                    System.out.print("Enter the amount to withdraw: ");
                    double withdrawAmount = scanner.nextDouble();
                    if (withdrawAmount > 0 && account.withdraw(withdrawAmount)) {
                        System.out.println("Withdrawal successful! New balance: $" + account.getBalance());
                    } else {
                        System.out.println("Withdrawal failed. Insufficient funds or invalid amount.");
                    }
                    break;

                case 2: // Deposit
                    System.out.print("Enter the amount to deposit: ");
                    double depositAmount = scanner.nextDouble();
                    if (depositAmount > 0) {
                        account.deposit(depositAmount);
                        System.out.println("Deposit successful! New balance: $" + account.getBalance());
                    } else {
                        System.out.println("Deposit failed. Please enter a valid amount.");
                    }
                    break;

                case 3: // Check Balance
                    System.out.println("Your current balance is: $" + account.getBalance());
                    break;

                case 4: // Exit
                    System.out.println("Thank you for using the ATM. Goodbye!");
                    exit = true;
                    break;

                default:
                    System.out.println("Invalid option. Please try again.");
                    break;
            }
        }

         scanner.close();
    }
}

public class ATMSystem {
    public static void main(String[] args) {
        // Initialize a bank account with a starting balance of $500
        BankAccount userAccount = new BankAccount(500.0);

        // Create an ATM connected to the user's account
        ATM atm = new ATM(userAccount);

        // Start the ATM interface
        atm.start();
    }
}
