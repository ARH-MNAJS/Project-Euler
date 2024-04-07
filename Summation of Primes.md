# Summation of Primes

## Question
The sum of the primes below 10 is 2+3+5+7=17.
Find the sum of all the primes below two million.

## Answer
``` java
public class SumOfPrimes {

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
        long sum = 0;
        for (int i = 2; i < 2000000; i++) {
            if (isPrime(i)) {
                sum += i;
            }
        }
        System.out.println("The sum of all primes below two million is: " + sum);
    }
}
```
