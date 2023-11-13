# Smallest Multiple

## Question
2520 is the smallest number that can be divided by each of the numbers from 1 to 10 without any remainder.
What is the smallest positive number that is evenly divisible by all of the numbers from 1 to 20?

## Answer
``` java
public class Main {
    public static void main(String[] args) {
        int number = 2520;

        while (true || number%2 == 0) {
            boolean isDivisible = true;
            for (int i = 1; i <= 20; i++) {
                if (number % i != 0) {
                    isDivisible = false;
                    break;
                }
            }
            if (isDivisible) {
                System.out.println("The smallest number divisible by all numbers from 1 to 20 is: " + number);
                break;
            }
            number++;
        }
    }
}

```
