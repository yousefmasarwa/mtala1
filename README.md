# mtala1
import java.util.Scanner;

import static java.lang.Math.min;
import static java.lang.Math.sqrt;

public class Ex1 {

    static private boolean isPrime(int a) {
        for (int i = 2; i <= sqrt(a); ++i) {
            if (a % i == 0) {
                return false;
            }
        }
        return true;
    }

    static int primeGCD(int a, int b) {
        int PGCD = 0;
        for (int i = 2; i < min(a, b); i++) {
            if (isPrime(i) && a % i == 0 && b % i == 0) {
                PGCD = i;
            }
        }
        return PGCD;
    }

    public static void main(String[] args) {
        int a, b;
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the first number: ");
        a = scanner.nextInt();
        System.out.print("Enter the second number: ");
        b = scanner.nextInt();
        int gcd = Ex1.primeGCD(a, b);
        System.out.println("Computes the GPCD(" + a + "," + b + ") =");
        System.out.print("Max prime common divider: " + gcd);
    }
}
