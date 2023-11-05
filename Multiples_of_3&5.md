# Multiples of 3 & 5

## Question
If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3,5, 6 and 9. The sum of these multiples is 23.
Find the sum of all the multiples of 3 or 5 below 1000.

## Answer
``` java
import java.util.*;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int size = sc.nextInt();
        int sum = 0;
        for(int i=0; i<size; i++){
            if (i%3 == 0 || i%5 == 0){
                sum += i;
            }
        }
        System.out.println(sum);
    }
}
```





