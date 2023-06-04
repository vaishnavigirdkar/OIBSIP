package internShip;

//Name: Vaishnavi Giradkar
import java.util.Scanner;
public class AtmInterfaceJava {
 

public static void main( String args[] ) {
//declare and initialize balance, withdraw, and deposit
int balance = 100000;
int withdraw, deposit,transfer,number;
//create scanner class object to get choice of user
Scanner sc = new Scanner(System.in);
while(true)
{
System.out.println( "Welcome to ATM ... " );
System.out.println( "Select 1 for Withdraw" );
System.out.println( "Select 2 for Deposit" );
System.out.println( "Select 3 for Money Transfer");
System.out.println( "Select 4 for Check Balance" );
System.out.println( "Select 5 for EXIT" );
System.out.print( "Select the appropriate options you want to perform:" );
//get the user selected option
int op = sc.nextInt( );
switch( op )
{
case 1 -> {
  System.out.print( "Enter the amount to be withdrawn :" );
  // accept the withdraw amount from the user
  withdraw = sc.nextInt();
  //check whether the balance is greater than or equal to the withdrawal amount
  withdraw( balance, withdraw);
      }
case 2 -> {
  System.out.print( "Enter the amount to be deposited :" );
  //accept the deposit amount from the user
  deposit = sc.nextInt();
  // call the function and add the deposit amount to the total balance
  deposit( balance, deposit );
      }
case 3 ->{
  System.out.println("Enter the account number: ");
  //accept the transfered amount from user
  number=sc.nextInt();
  System.out.println("Enter the amount to be transfered: ");
  //accept the transfered amount from user
  transfer=sc.nextInt();
  transfer( balance, transfer);
}
case 4 -> {
  // printing the total balance of the user
  printBalance( balance );
  System.out.println(" ");
      }
case 5 -> // exit from the menu
  System.exit( 0 );
}
}
}
//function to print the current balance in an account
public static void printBalance(int balance)
{
System.out.println(" The Current Balance : " + balance);
System.out.println();
}
//The function to Withdraw an amount and update the balance
public static int withdraw(int balance, int withdrawAmount)
{
System.out.println( "Withdrawn Operation :" );
System.out.println("The withdrawing Amount is : " + withdrawAmount);
if (balance >= withdrawAmount) {
balance = balance - withdrawAmount;
System.out.println( "Please collect your money and remove the card" );
printBalance( balance );
}
else {
System.out.println( "Sorry! the balanace is insufficient." );
System.out.println( );
}
return balance;
}
//The function to transfer an amount and update the balance
public static int transfer(int balance, int transferAmount)
{   
System.out.println( "Transfer Operation :" );   
System.out.println(" The transfering amount is : " + transferAmount);
if (balance >= transferAmount) {
balance = balance - transferAmount;
System.out.println( "The money is successfully transfered" );
printBalance( balance );
}
else {
System.out.println( "Sorry! the balanace is insufficient." );
System.out.println( );
}
return balance;
}

//The function to deposit an amount and update the balance
public static int deposit(int balance, int depositAmount)
{
  
System.out.println( "Deposit Operation :" );
System.out.println(" The depositing amount is : " + depositAmount);
balance = balance + depositAmount;
System.out.println( "Your Money has been successfully deposited" );
printBalance(balance);
return balance;
}
}
