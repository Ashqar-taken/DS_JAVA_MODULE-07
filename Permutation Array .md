# Ex9 Finding the Longest Length of Nested Set in a Permutation Array
## DATE: 04.08.2026
## AIM:
To write a program that finds the length of the longest set s[k] defined as s[k] = { nums[k], nums[nums[k]], nums[nums[nums[k]]], … },where the iteration stops before a duplicate element occurs.

The task is to return the maximum size among all such sets.
## Algorithm
1. Define a method to find the maximum size of all permtation of sets.
2. Create a boolean array visited of size n. It keeps track of indices/elements that have already been explored.
3. Initialize max =0, it stores the length of the longest set found so far.
4. Traverse every index, If visited[i] is true, skip it because this cycle has already been explored.
5. tart the current cycle, Set curr = i and Set count = 0.
6. While curr has not been visited. Mark curr as visited, Increment count, Move to the next index using:
7. Stop when a visited index is reached
8. Update the maximum, Compare count with max.
9. Return the maximum

## Program:
```
/*
Program to find the Longest Length of Nested Set in a Permutation Array
Developed by: Ashqar Ahamed S T
RegisterNumber: 212224240018
*/

import java.util.*;
public class ArrayNestingMain {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String input = sc.nextLine().trim();
        input = input.replace("nums =", "").replace("[", "").replace("]", "").trim();
        String[] parts = input.split(",");
        int[] nums = new int[parts.length];

        for (int i = 0; i < parts.length; i++) {
            nums[i] = Integer.parseInt(parts[i].trim());
        }
        Solution sol = new Solution();
        int result = sol.arrayNesting(nums);
        System.out.println(result);
        sc.close();
    }
}
class Solution {
    public int arrayNesting(int[] nums) {
        
        boolean[] visited = new boolean[nums.length];
        int max = 0;
        
        for(int i=0;i<nums.length;i++)
        {
            if(visited[i])
                continue;
            
            int curr = i;
            int count = 0;
            
            while(!visited[curr])
            {
                visited[curr] = true;
                count++;
                curr = nums[curr];
            }
            
        max = Math.max(max,count);
        
        }
        
        return max;
      
      
    }
    
}


```

## Output:

<img width="606" height="197" alt="output Day4" src="https://github.com/user-attachments/assets/27bf1083-b295-47d4-a928-e523b76b7e21" />


## Result:
The program successfully computes the longest length of the nested set s[k] for the given permutation array.
