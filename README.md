#include <iostream>

// Function to calculate the sum of all integers between 'first' and 'last', inclusive
int sum_from_to(int first, int last) {
    if (first > last) {
        std::swap(first, last); // Ensure 'first' is less than or equal to 'last'
    }

    int sum = 0;
    for (int i = first; i <= last; i++) {
        sum += i;
    }

    return sum;
}

// Helper function to find the greatest common divisor (GCD) using the Euclidean algorithm
int gcd(int a, int b) {
    while (b != 0) {
        int temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}

// Function to reduce a fraction by dividing 'num' and 'denom' by their GCD
int reduce(int &num, int &denom) {
    if (num <= 0 || denom <= 0) {
        return 0; // Failure to reduce if either is zero or negative
    }

    int divisor = gcd(num, denom);
    num /= divisor;
    denom /= divisor;
    return 1; // Indicate successful reduction
}

int main() {
    // Example usage of sum_from_to
    int first = 5, last = 10;
    int sum = sum_from_to(first, last);
    std::cout << "Sum from " << first << " to " << last << " is: " << sum << std::endl;

    // Example usage of reduce
    int num = 8, denom = 12;
    int result = reduce(num, denom);
    if (result == 1) {
        std::cout << "Reduced fraction: " << num << "/" << denom << std::endl;
    } else {
        std::cout << "Failed to reduce the fraction." << std::endl;
    }

    return 0;
}



![Screenshot 2024-08-31 141329](https://github.com/user-attachments/assets/745f3a8b-2659-4d8a-b1e8-d1c911cb9f1c)
