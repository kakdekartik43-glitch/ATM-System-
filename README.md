# ATM-System-
#include <stdio.h>

int main() 
{
    int pin = 1234, enteredPin;
    int choice;
    float balance = 5000.0;
    float amount;

    printf("===== Welcome to ATM =====\n");

    printf("Enter your PIN: ");
    scanf("%d", &enteredPin);

    if (enteredPin == pin) 
    {
        do 
        {
            printf("\n----- ATM Menu -----\n");
            printf("1. Check Balance\n");
            printf("2. Deposit Money\n");
            printf("3. Withdraw Money\n");
            printf("4. Exit\n");
            printf("Enter your choice: ");
            scanf("%d", &choice);

            switch(choice) 
            {
                case 1:
                    printf("Your Balance is: %.2f\n", balance);
                    break;

                case 2:
                    printf("Enter amount to deposit: ");
                    scanf("%f", &amount);
                    balance += amount;
                    printf("Amount Deposited Successfully!\n");
                    break;

                case 3:
                    printf("Enter amount to withdraw: ");
                    scanf("%f", &amount);
                    if(amount <= balance) 
                    {
                        balance -= amount;
                        printf("Please collect your cash.\n");
                    } 
                    else 
                    {
                        printf("Insufficient Balance!\n");
                    }
                    break;

                case 4:
                    printf("Thank you");
break;

                default:
                    printf("Invalid Choice!\n");
            }

        } while(choice != 4);
    } 
    else 
    {
        printf("Incorrect PIN!\n");
    }

    return 0;
}