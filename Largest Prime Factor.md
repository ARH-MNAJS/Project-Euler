# Even Fibonacci Numbers

## Question
The prime factors of 13195 are 5, 7, 13 and 29.
What is the largest prime factor of the number 600851475143?

## Answer
``` java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        long num = sc.nextLong();
        ArrayList<Long> arr = new ArrayList<>();
        long f_num = (long) Math.floor(Math.sqrt(num));
        System.out.println(f_num);
        for (long i = 1; i <= f_num; i++) {
            if (num % i == 0) {
                arr.add(i);
                arr.add(num / i);
            }
        }

        ArrayList<Long> factors = new ArrayList<>();
        long largestPrime = 0;

        for (int i = 0; i < arr.size(); i++) {
            if (isPrime(arr.get(i))) {
                factors.add(arr.get(i));
                if (arr.get(i) > largestPrime) {
                    largestPrime = arr.get(i);
                }
            }
        }

        if (!factors.isEmpty()) {
            System.out.println("Prime Factors in the ArrayList: " + factors);
            System.out.println("Largest Prime Factor: " + largestPrime);
        } else {
            System.out.println("No prime factors found.");
        }
    }

    public static boolean isPrime(long num) {
        if (num <= 1) {
            return false;
        }
        if (num <= 3) {
            return true;
        }
        if (num % 2 == 0 || num % 3 == 0) {
            return false;
        }
        for (long i = 5; i * i <= num; i += 6) {
            if (num % i == 0 || num % (i + 2) == 0) {
                return false;
            }
        }
        return true;
    }
}

```
