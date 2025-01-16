# Java-Practice

To reverse the given number:

import java.util.Scanner;

public class Main {
    
     public static void main(String[] args) {
     
     Scanner input = new Scanner(System.in);
     System.out.println("Enter number");
     int n = input.nextInt();
       
     input.close();

     int reversed = 0;

     while (n > 0) {
      int digit = n%10;
       reversed = reversed * 10 + digit;
          n = n/10;
         }
    System.out.println(reversed);
    
  }
  
  }
