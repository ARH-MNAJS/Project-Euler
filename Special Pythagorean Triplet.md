# Special Pythagorean Triplet

## Question
There exists exactly one Pythagorean triplet for which a+b+c=1000. Find the product abc

## Answer
``` java
public class Program {

    public static void main(String[] args) {
        for (long i = 1; i < 1000; i++) {
            for (long j = i; j < 1000; j++) {
                for (long k = j; k < 1000; k++) {
                    if ((i*i)+(j*j) == (k*k) && (i+j+k)==1000) {
                        System.out.println(i*j*k);   
                    }
                }
            }
        }
    }
}

```
