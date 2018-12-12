/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package ATM;
import java.util.Scanner;
/**
 *
 * @author Jeremy
 */
public class ATM {
    public static void main(String[] args) {
        System.out.println("Hello and Welcome to Jeremy's ATM simulator!");
        while(true){
        double balance = 4268.19;
        double checking = 700.47;
        double savings = 3567.72;
        System.out.println("Would you like to 1)Check your balance, 2)Access your Checking account, "
                + "3)Access your Savings account, 4)Transfer funds, "
                + "5)Withdraw, 6)Fast cash ($60), 7)End the program");
       Scanner scan = new Scanner(System.in);
       int userInput = scan.nextInt();
        if(userInput == 1){
            checkBalance(balance);
        }//close check balance IF
        if(userInput == 2){
            checkChecking(checking);
        }//close checking If
        if(userInput == 3){
            checkSavings(savings);
        }//close checkSavings If
        if(userInput == 4){
            transferFunds(checking, savings);
        }//close transferFunds If
        if(userInput == 5){
            withdrawFunds(checking, savings);
        }//close withdrawFunds
        if(userInput == 6){
            fastCash(checking);
        }
        if(userInput == 7){
            System.out.println("Thank you for trying Jeremy's ATM simulator!");
            System.exit(0);
        }
      }   
        
        
        
        
    }//close main
    public static void checkBalance(double balance){
        
        System.out.println("Your available balance is: $" + balance);//Tells you your balance
        
         }//close checkBalance
    
    
    public static void checkChecking(double checking){
        System.out.println("Your available balance in your checking account is: $" + checking);
    }//close checkChecking
    
    public static void checkSavings(double savings){
        System.out.println("Your available balcance in your savings account is: $" + savings);
    }//close checkSavings
    
    public static void transferFunds(double checking, double savings){
        System.out.println("Would you like to transfer funds from your checking account to your savings? (Y/N)");
        Scanner scan = new Scanner(System.in);
        String userInput = scan.next(); 
        if(userInput.equals("y")){
            System.out.println("How much would you like to transfer from your checking to your savings?");
            double checkingToSavings = scan.nextDouble();
            System.out.println("Processing.....");
            checking = checking - checkingToSavings;
            savings = checkingToSavings + savings;
            System.out.println("Your new Checking account balance is: $" + checking);
            System.out.println("Your new Saving account balance is: $" + savings);
        }else {
                
            //end checking to savings yes and begin else for savings
            System.out.println("How much would you like to transfer from your savings to your checking?");
            double savingsToChecking = scan.nextDouble();
            System.out.println("Processing.....");
            savings = savings - savingsToChecking;
            checking = savingsToChecking + checking;
            System.out.println("Your new Saving account balance is: $" + savings);
            System.out.println("Your new Checking account balance is: $" + checking);
     
    }//end savings to checking account Else
  }//end transfer funds
    
    public static void withdrawFunds(double checking, double savings){
        System.out.println("Would you like to withdraw from your checking account? (Y/N)");
        Scanner scan = new Scanner(System.in);
        String withdrawInput = scan.next();
        if(withdrawInput.equals("y")){
            System.out.println("How much would you like to withdraw from your checking account? Your available balance is: $" + checking);
            double withdrawAmountChecking = scan.nextDouble();
            System.out.println("Processing.....");
            checking = checking - withdrawAmountChecking;
            System.out.println("Your new checking account balance is: $" + checking);
            System.out.println("DON'T FORGET YOUR MONEY!!!!");
        }else{
            System.out.println("How much would you like to withdraw from your savings acccount? Your available balance is: $" + savings);
            Double withdrawAmountSavings = scan.nextDouble();
            System.out.println("Processing.....");
            savings = savings - withdrawAmountSavings;
            System.out.println("Your new savings account balance is: $" + savings);
            System.out.println("DON'T FORGET YOUR MONEY!!!!");
        }//end if/else for withdrawFunds
    }//end withdrawFunds
    
    public static void fastCash(double checking){
        int fastCash = 60;
        System.out.println("Fast cash pulls directly from your checking account would you like to continue?");
        Scanner scan = new Scanner(System.in);
        String fastCashYesNo = scan.next();
        if(fastCashYesNo.equals("y")){
            checking = checking - fastCash;
            System.out.println("Your new checking account balance is: $" + checking);
        }else{
        }//end if/else fastCash

    }//end fastCash
}//end class

