# Largest Palindrome Product

## Question
A palindromic number reads the same both ways. The largest palindrome made from the product of two 2-digit numbers is
9009 = 91 × 99.
Find the largest palindrome made from the product of two 3-digit numbers.

## Answer
``` java
public class Main {
    public static boolean isPalindrome(int product) {
        int originalProduct = product;
        int reverse = 0;
        while (product != 0) {
            reverse = reverse * 10 + product % 10;
            product /= 10;
        }
        return originalProduct == reverse;
    }

    public static void main(String[] args) {
        int upper_limit = (int) Math.pow(10, 3) - 1;
        int lower_limit = 1 + upper_limit / 10;
        int max_product = 0;
        for (int i = upper_limit; i >= lower_limit; i--) {
            for (int j = lower_limit; j <= upper_limit; j++) {
                int product = i * j;
                if (product > max_product && isPalindrome(product)) {
                    max_product = product;
                }
            }
        }
        System.out.println(max_product);
    }
}
```
