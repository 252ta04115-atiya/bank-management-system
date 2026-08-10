#include <stdio.h>

int main() {
    int choice;
    float balance = 0, amount;

    printf("===== BANKING SYSTEM =====\n");

    do {
        printf("\n1. Deposit Money");
        printf("\n2. Withdraw Money");
        printf("\n3. Check Balance");
        printf("\n4. Exit");

        printf("\n\nEnter your choice: ");
        scanf("%d", &choice);

        switch(choice) {

            case 1:
                printf("Enter amount to deposit: ");
                scanf("%f", &amount);

                if(amount > 0) {
                    balance = balance + amount;
                    printf("Amount Deposited Successfully!\n");
                    printf("Current Balance = %.2f\n", balance);
                }
                else {
                    printf("Invalid amount!\n");
                }
                break;

            case 2:
                printf("Enter amount to withdraw: ");
                scanf("%f", &amount);

                if(amount <= 0) {
                    printf("Invalid amount!\n");
                }
                else if(amount > balance) {
                    printf("Insufficient Balance!\n");
                }
                else {
                    balance = balance - amount;
                    printf("Amount Withdrawn Successfully!\n");
                    printf("Current Balance = %.2f\n", balance);
                }
                break;

            case 3:
                printf("Available Balance = %.2f\n", balance);
                break;

            case 4:
                printf("Thank you for using our banking system!\n");
                break;

            default:
                printf("Invalid Choice!\n");
        }

    } while(choice != 4);

    return 0;
}
