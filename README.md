Array
LEVEL 1
Find largest element
Find smallest element
Sum of array
Average
Count even/odd

Find Maximum Element
public class MaximumElement {

    public static void main(String[] args) {

        int[] arr = {4, 8, 1, 9, 3};

        int max = arr[0];

        for(int i = 1; i < arr.length; i++) {

            if(arr[i] > max) {
                max = arr[i];
            }
        }

        System.out.println("Maximum Element: " + max);
    }
}
 
Find Minimum Element
public class MinimumElement {

    public static void main(String[] args) {

        int[] arr = {4, 8, 1, 9, 3};

        int min = arr[0];

        for(int i = 1; i < arr.length; i++) {

            if(arr[i] < min) {
                min = arr[i];
            }
        }

        System.out.println("Minimum Element: " + min);
    }
}
 
Sum of Array
public class SumArray {

    public static void main(String[] args) {

        int[] arr = {1,2,3,4,5};

        int sum = 0;

        for(int i = 0; i < arr.length; i++) {
            sum += arr[i];
        }

        System.out.println("Sum: " + sum);
    }
}


Average 
 
public class AverageArray {
    public static void main(String[] args) {
        
        int[] arr = {10, 20, 30, 40, 50};
        
        int sum = 0;
        
        for (int i = 0; i < arr.length; i++) {
            sum = sum + arr[i];
        }
        
        double average = (double) sum / arr.length;
        
        System.out.println("Average = " + average);
    }
}

Count even/odd
public class EvenOddCount {
    public static void main(String[] args) {

        int[] arr = {10, 15, 20, 25, 30, 35};

        int evenCount = 0;
        int oddCount = 0;

        for (int i = 0; i < arr.length; i++) {

            if (arr[i] % 2 == 0) {
                evenCount++;
            } else {
                oddCount++;
            }
        }

        System.out.println("Even numbers count = " + evenCount);
        System.out.println("Odd numbers count = " + oddCount);
    }
}

LEVEL 2
Reverse array
Swap alternate element
Move zeros
Rotate array

Reverse Array
import java.util.*;

public class ReverseArray {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5};

        int start = 0;
        int end = arr.length - 1;

        while (start < end) {
            int temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;

            start++;
            end--;
        }

        System.out.println(Arrays.toString(arr));
    }
}

Swap Alternate Elements

public class SwapAlternate {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5, 6};

        for (int i = 0; i < arr.length - 1; i += 2) {
            int temp = arr[i];
            arr[i] = arr[i + 1];
            arr[i + 1] = temp;
        }

    }
}

Move Zeros 
class Solution {
    void pushZerosToEnd(int[] arr) {
        // code here
        int count = 0;
        
        for(int i = 0; i < arr.length; i++){
            if(arr[i] != 0){
                int temp = arr[i];
                arr[i] = arr[count];
                arr[count] = temp;
                count++;
            }
        }
    }
}

Rotate Array 
class Solution {
    static void rotateArr(int arr[], int d) {
        // code here
        int n = arr.length;
        d %= n;
        
        reverse(arr,0,d-1);
        reverse(arr,d,n-1);
        reverse(arr,0,n-1);
    }
        static void reverse(int arr[], int start, int end){
            while(start<end){
                int temp = arr[start];
                arr[start] = arr[end];
                arr[end] = temp;
                start++;
                end--;
            }
        }
}

LEVEL 3
Second largest
Remove duplicates
Two sum
Missing number 
Majority element

Second Largest Element
class Solution {
    public int getSecondLargest(int[] arr) {
        // code here
        int n = arr.length;
        int largest = -1;
        int secondLargest = -1;
        for(int i = 0; i < arr.length; i++){
            if(arr[i] > largest){
                secondLargest = largest;
                largest = arr[i];
            }
            else if(arr[i]>secondLargest && arr[i]<largest){
                secondLargest = arr[i];
            }
        }
        return secondLargest;
    }
}

Remove Duplicates from Sorted Array
class Solution {
    ArrayList<Integer> removeDuplicates(int[] arr) {
        // code here
        int n = arr.length;
        ArrayList<Integer> ans = new ArrayList<>();
        if(n == 0){
            return ans;
        }
        ans.add(arr[0]);
        for(int i = 1; i < n; i++){
            if(arr[i] != arr[i-1]){
                ans.add(arr[i]);
            }
        }
        return ans;
    }
}

Two Sum
import java.util.*;

class Solution {
    public int[] twoSum(int[] nums, int target) {
       int l = 0, r = nums.length - 1;
       while(l < r){
        int sum = nums[l] + nums[r];
        if(sum == target)
            return new int[] {l,r};

        else if(sum < target)
           l++;
        else
           r--;
       }
       return new int[] {};
    }
}

Missing Number
class Solution {
    public int missingNumber(int[] nums) {
        Arrays.sort(nums);
        for(int i=0; i<nums.length; i++){
           if(nums[i]!= i){
            return i;
           }
        }
        return nums.length;
    }

Majority Element
class Solution {
    public int majorityElement(int[] nums) {
        int count = 0;
        int candidate = 0;
        for(int num : nums){
            if(count == 0){
                candidate = num;
            }

            if(num == candidate){
                count++;
            }

            else{
                count--;
            }
        }
        return candidate;
    }
}

