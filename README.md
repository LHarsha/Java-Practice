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


To check consecutive numbers matching the target or not:

import java.util.Scanner;

public class TwoSum {
    public static void main(String[] args) {

    Scanner input = new Scanner(System.in);
    System.out.println("Enter Number Of Digits");
    int n = input.nextInt();
    int[] nums = new int[n];

    System.out.println("Enter Digits");
    int i = 0;
    while (i<n) {
        nums[i] = input.nextInt();
        i++;
    }
    
    System.out.println("Enter Target");
    int target = input.nextInt();

    boolean found = false;

    for(i = 0; i < n-1; i++) {
       
        int sum =  nums[i] +nums[i+1];
        if (sum == target)
        {
             System.out.println("Digits are: " +nums[i] +" " +nums[i+1]);
            
         found = true;
            break;
        }

     }
 
     if (!found) {
       System.out.println("No consecutive digits sum upto target");
     }

 input.close();
    }
}

