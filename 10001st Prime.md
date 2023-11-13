# 10001st Prime

## Question
By listing the first six prime numbers: 2, 3, 5, 7, 11, and 13, we can see that the 6th prime is 13.
What is the 10001st prime number?

## Answer
``` java
import java.util.*;

public class Main {

    // Function to check if a number is prime
    public static boolean isPrime(int number) {
        if (number <= 1) {
            return false;
        }
        for (int i = 2; i * i <= number; i++) {
            if (number % i == 0) {
                return false;
            }
        }
        return true;
    }

    public static void main(String[] args) {
        int num = 1; // You can change this number to check for other values
        ArrayList<Integer> primes = new ArrayList<Integer>();
        boolean searching = true;
        while (searching) {
            if (isPrime(num)) {
                primes.add(num);
                num++;
            } else {
                num++;
            }
            if (primes.size() == 10001) {
                searching = false;
                System.out.println(primes.get(primes.size() - 1));
            }
        }
    }
}

```
