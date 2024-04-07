# Highly Divisible Triangular Number

## Question
What is the value of the first triangle number to have over five hundred divisors?

## Answer
``` java
public class Program {
    public static void main(String[] args) {
        int result = findTriangleNumberWithOver500Divisors();
        System.out.println("The first triangle number with over 500 divisors is: " + result);
    }

    public static int countDivisors(int n) {
        int count = 0;
        for (int i = 1; i <= Math.sqrt(n); i++) {
            if (n % i == 0) {
                count += 2; 
            }
        }
        if (Math.pow((int) Math.sqrt(n), 2) == n) {
            count--;
        }
        return count;
    }

    public static int findTriangleNumberWithOver500Divisors() {
        int triangleNumber = 0;
        int increment = 1;

        while (true) {
            triangleNumber += increment;
            increment++;
            int divisorsCount = countDivisors(triangleNumber);
            if (divisorsCount > 500) {
                break;
            }
        }

        return triangleNumber;
    }
}
```
