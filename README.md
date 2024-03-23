public class Account {
    private double balance;
    private String history;

    public Account(double balance) {
        this.balance = balance;
    }

    public void deposit(double amount) {
        this.balance += amount;
        this.history += "Deposit: $" + amount + "\n";
    }

    public void withdraw(double amount) {
        if (this.balance >= amount) {
            this.balance -= amount;
            this.history += "Withdraw: $" + amount + "\n";
        } else {
            System.out.println("Insufficient balance");
        }
    }

    public void display() {
        System.out.println("Saldo: $" + balance);
        System.out.println("History:");
        System.out.println(this.history);
    }
}

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        Account userAccount = new Account(95_000.0);
        userAccount.display();

        System.out.println("Enter username: abc");
        System.out.println("Enter password: 12345");
        System.out.println("What do you want to do? (1) Deposit, (2) Withdraw");

        int choice = input.nextInt();
        if (choice == 1) {
            System.out.println("How much do you want to deposit?");
            double amount = input.nextDouble();
            userAccount.deposit(amount);
            userAccount.display();
        } else if (choice == 2) {
            System.out.println("How much do you want to withdraw?");
            double amount = input.nextDouble();
            userAccount.withdraw(amount);
            userAccount.display();
        }
    }
}
}
