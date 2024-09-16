# ATM-machine
 //Developed an simple project that is ATM machine simulation using Java. Implemented core functionalities such as account balance checking, cash withdrawal, deposit, and transaction history using classes and objects.

 //code----

class ATM{
     float Balance;
     int Pin=1234;

      public void checkpin(){
        System.out.println("enter ur pin");
        Scanner sc=new Scanner(System.in);
        int enterdpin=sc.nextInt();
        if(enterdpin==Pin){
            menu();
        }
        else {
            System.out.println("enter a valid pin");
            menu();
        }
      }

      public void menu(){
        System.out.println("Enter ur choice");
        System.out.println("1.check A/C Balance");
        System.out.println("2.Withdraw money");
        System.out.println("3.Deposite money");
        System.out.println("4.Exit");

        Scanner sc= new Scanner(System.in);
        int opt=sc.nextInt();

        if(opt==1){
            checkBalance();
        }
        else if(opt==2){
            withdrawMoney();
        }
        else if(opt==3){
            depositeMoney();
        }
        else if(opt==4){
            return;
        }
        else{
            System.out.println("Enter a valid choice");
        }
      }


      public void checkBalance(){
          System.out.println("Balance " +Balance);
          menu();    
      }

      public void withdrawMoney(){
          System.out.println("enter amount to withdraw");
          Scanner sc=new Scanner(System.in);
          float amount=sc.nextInt();

          if(amount>Balance){
            System.out.println("insufficient balance");
          }
          else{
            Balance=Balance-amount;
            System.out.println("money withdrawl successfully");
          }
          menu();
      }

      public void depositeMoney(){
        System.out.println("enter the amount");
        Scanner sc=new Scanner(System.in);
        float amount=sc.nextFloat();
        Balance=Balance+amount;
        System.out.println("money deposited successfully");
        menu();
      }
}


public class ATMMachine{
    public static void main(String[] args){
        ATM obj=new ATM();
        obj.checkpin();
    }
}
