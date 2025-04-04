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


Binary search: 

public class TwoSum {


    public static void main(String[] args) {

    int[] arr = {1, 2, 4, 6, 8, 14, 26, 33};    
    int target = 14;
    int ans = binarySearch(arr, target);
    System.out.println(ans);
    }

    static int binarySearch (int[] arr, int target) {
    int start = 0;
    int end = arr.length - 1;

    while (start <= end) {
     
        int mid = (start + end)/2;
       if (target > arr[mid]) {
        start = mid + 1;
       }
       else if (target < arr[mid]) {
        end = mid -1;
       }
       
        else {
        return mid;
        }
    }
    return -1;
       }
    }    

Infinite sorted array: 

public class infiniteArr {
    public static void main(String args[]) {
      int[] arr = {2, 3, 4, 5, 7, 12, 16, 17, 33, 36, 40, 45};
      int target = 33;
      
          // 9
      System.out.println("target is at index " +Double(arr, target));
    }

    static int Double(int arr[], int target){
        
        int start = 0;
        int end = 1;
        
        while (end < arr.length && target >= arr[end]){
            int newStart = end + 1;
            end = end + (end- start + 1)*2;
            start = newStart;
        }
        return findTarget(arr, target, start, end);
    }

    static int findTarget(int[] arr, int target, int start, int end) {
    
    while(start <= end){
    int mid = start + (end - start) / 2;

    if(target > arr[mid] ) {
        start = mid + 1;
    } else if(target < arr[mid]){
        end = mid - 1;
    } else {
        return mid;
    }

    }
    return -1;
    }
}

MATRIX BINARY SEARCH:

import java.util.Arrays;

public class MatrixBinary {
    public static void main(String[] args){
        int[][] arr = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        System.out.println(Arrays.toString(search(arr, 6)));
    }


static int[] binarySearch(int[][] matrix, int row, int cStart, int cEnd, int target) {

    while (cStart <= cEnd) {
      
        int mid = cStart + (cEnd - cStart)/2;
      
        if (matrix[row][mid] == target) {
        return new int[] {row, mid};
      
    } if (matrix[row][mid] > target){
        cEnd = mid - 1; 
      } else {
        cStart = mid + 1;
      }
    }
    return new int[] {-1, -1};
}
static int[] search(int[][] matrix, int target) {
    int rows = matrix.length;
    int cols = matrix[0].length;

    if (rows == 1) {
     return binarySearch(matrix, 0, 0, cols - 1, target);
    }

    int rStart = 0;
    int rEnd = rows - 1;
    int cMid = cols / 2;

    while (rStart < (rEnd - 1) ) {

        int mid = rStart + (rEnd - rStart) / 2;
        
        if (matrix[mid][cMid] == target) {
            return new int[]{mid, cMid};
         }
        if (matrix[mid][cMid] < target) {
            rStart = mid;
        } else {
            rEnd = mid;
        }
    }
 
    if (matrix[rStart][cMid] == target) {
        return new int[] {rStart, cMid};
    }
    if (matrix[rStart + 1][cMid] == target) {
        return new int[]{rStart + 1, cMid};
    }

    if (target <=  matrix[rStart][cMid - 1]) {
        return binarySearch(matrix, rStart, 0, cMid -1, target);
    }
    if (target >= matrix[rStart][cMid + 1] && target <= matrix[rStart][cols - 1]) {
        return binarySearch(matrix, rStart, cMid -1, cols -1, target);
    }
    if (target <= matrix[rStart + 1][cMid - 1]) {
        return binarySearch(matrix, rStart + 1, 0, cMid - 1, target);
    }
    else {
        return binarySearch(matrix, rStart + 1, cMid + 1, cols - 1, target);
    }
  }
}


BUBBLE SORT ALGORITHM: 

public class Bubble {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 5, 4, 6};
       
        bubbleSort(arr);

        for (int num : arr) {
            System.out.print(num + " ");
        }
    }


static void bubbleSort(int[] arr) {

    int k = 0;
    int n = arr.length;

    for (int i = 0; i < n - 1; i++) {

     for (int j = 0; j < n - i - 1; j++) {
       if (arr[j] > arr[j + 1]) {
        k = arr[j];
        arr[j] = arr[j + 1];
        arr[j + 1] = k;
        
       }
      }
    }
  }
}
