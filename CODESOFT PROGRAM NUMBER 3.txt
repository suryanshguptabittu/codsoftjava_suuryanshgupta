import java.util.Scanner;

class BankAccount {
    private double balance;

    public BankAccount(double balance) {
        this.balance = balance;
    }

    public String deposit(double amount) {
        if(amount <= 0) {
            return "Invalid deposit amount";
        }
        this.balance += amount;
        return "Deposited $" + amount + ". New Balance: $" + this.balance;
    }

    public String withdraw(double amount) {
        if(amount <= 0) {
            return "Invalid withdrawal amount";
        }
        if(this.balance < amount) {
            return "Insufficient balance";
        }
        this.balance -= amount;
        return "Withdrew $" + amount + ". New Balance: $" + this.balance;
    }

    public String checkBalance() {
        return "Your current balance is $" + this.balance;
    }
}

class ATM {
    private BankAccount account;
    private Scanner scanner;

    public ATM(BankAccount account) {
        this.account = account;
        this.scanner = new Scanner(System.in);
    }

    public void displayMenu() {
        System.out.println("ATM Menu:");
        System.out.println("1. Check Balance");
        System.out.println("2. Deposit");
        System.out.println("3. Withdraw");
        System.out.println("4. Exit");
    }

    public void userInterface() {
        while(true) {
            displayMenu();
            System.out.print("Select an option: ");
            int choice = scanner.nextInt();
            switch(choice) {
                case 1:
                    System.out.println(account.checkBalance());
                    break;
                case 2:
                    System.out.print("Enter deposit amount: ");
                    double depositAmount = scanner.nextDouble();
                    System.out.println(account.deposit(depositAmount));
                    break;
                case 3:
                    System.out.print("Enter withdrawal amount: ");
                    double withdrawAmount = scanner.nextDouble();
                    System.out.println(account.withdraw(withdrawAmount));
                    break;
                case 4:
                    System.out.println("Thank you for using the ATM!");
                    return;
                default:
                    System.out.println("Invalid option selected. Try again.");
            }
        }
    }

    public static void main(String[] args) {
        BankAccount userAccount = new BankAccount(1000.0);  // Example starting balance is $1000
        ATM atmMachine = new ATM(userAccount);
        atmMachine.userInterface();
    }
}
