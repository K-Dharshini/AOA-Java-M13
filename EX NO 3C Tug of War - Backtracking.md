
# EX 3C Tug of War problem - Backtracking
## Date:
## Aim:
To write a Java program to for given constraints. Given an integer array nums, return true if you can partition the array into two subsets such that the sum of the elements in both subsets is equal or false otherwise.

**Example:**

**Input:** 
- Enter the number of elements: 4
- Enter the elements of the array: 1 5 11 5

**Output:** true

**Explanation:** The array can be partitioned as [1, 5, 5] and [11].

**Constraints:**

- 1 <= nums.length <= 200
- 1 <= nums[i] <= 100

## Algorithm
1. 
2. 
3. 
4.  
5.   

## Program:
```
Program to implement tug of war problem

Developed by: DHARSHINI K
Register Number: 212223230047

import java.util.Scanner;
public class Solution {
    public boolean canPartition(int[] nums) {
        if (nums.length == 0)
            return false;
        int totalSum = 0;
        for (int num : nums) {
            totalSum += num;
        }
        if (totalSum % 2 != 0)
            return false;
        int subSetSum = totalSum / 2;
        boolean[] dp = new boolean[subSetSum + 1];
        dp[0] = true;
        for (int curr : nums) {
            for (int j = subSetSum; j >= curr; j--) {
                dp[j] |= dp[j - curr];
            }
        }
        return dp[subSetSum];
    }
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Solution sol = new Solution();
        int n = scanner.nextInt();
        int[] nums = new int[n];
        for (int i = 0; i < n; i++) {
            nums[i] = scanner.nextInt();
        }
        boolean canBePartitioned = sol.canPartition(nums);
        System.out.println(canBePartitioned);
    }
}
```

## Output:
<img width="440" height="248" alt="image" src="https://github.com/user-attachments/assets/47745505-3618-435b-a0d1-b29c77c4910a" />

## Result:
The program was successfully implemented and the expected output is verified.
