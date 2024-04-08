# Longest Collatz Sequence

## Question
Which starting number, under one million, produces the longest chain for Collatz sequence?

## Answer
``` java
public class Program {
    public static void main(String[] args) {
        int maxLength = 0;
        int numberWithMaxLength = 0;
        
        for (int i = 1; i < 1000000; i++) {
            int length = calculateCollatzSequenceLength(i);
            if (length > maxLength) {
                maxLength = length;
                numberWithMaxLength = i;
            }
        }
        
        System.out.println("Starting number under one million that produces the longest Collatz sequence: " + numberWithMaxLength);
        System.out.println("Length of the sequence: " + maxLength);
    }
    
    public static int calculateCollatzSequenceLength(long n) {
        int length = 1;
        
        while (n != 1) {
            if (n % 2 == 0) {
                n = n / 2;
            } else {
                n = 3 * n + 1;
            }
            length++;
        }
        
        return length;
    }
}

```
