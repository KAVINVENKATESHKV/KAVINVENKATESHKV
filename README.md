#include <stdio.h>

// Define a structure for items
struct Item {
    char name[20];
    float price;
    int quantity;
};

int main() {
    // Declare variables
    struct Item items[10];
    int n = 0; // Number of items
    float totalBill = 0.0;

    // Add items
    printf("Enter the number of items: ");
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        printf("Enter item name, price, and quantity: ");
        scanf("%s %f %d", items[i].name, &items[i].price, &items[i].quantity);
        totalBill += items[i].price * items[i].quantity;
    }

    // Display bill details
    printf("Bill Details:\n");
    for (int i = 0; i < n; i++) {
        printf("%s x %d = %.2f\n", items[i].name, items[i].quantity, items[i].price * items[i].quantity);
    }
    printf("Total Bill: %.2f\n", totalBill);

    // Make payment
    float payment;
    printf("Enter payment amount: ");
    scanf("%f", &payment);
    totalBill -= payment;
    printf("Remaining balance: %.2f\n", totalBill);

    return 0;
}
