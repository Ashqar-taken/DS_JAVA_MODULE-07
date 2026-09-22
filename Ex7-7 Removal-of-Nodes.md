# Ex7 Removal of Nodes with a Specific Value from a Linked List
## DATE: 30.08.2026
## AIM:
To write a java  program that removes all nodes from a linked list whose value matches a given integer (val) and returns the new head of the modified linked list.

## Algorithm
1. Import the necessary libraries.
2. Create a linkedlist by defining the required methods such as insert, display.
3. Obtain the elements to insert into LinkedList from user
4. Define a method to remove the nodes with given value.
5. Traverse through the list and find if any nodes have the target value.
6. Use a prev pointer to make the previous node to point the next node, skipping the current node with the given target value.
7. Display the resultant LinkedList.

## Program:
```
/*
program that removes all nodes from a linked list whose value matches a given integer (val) and returns the new head of the modified linked list.
Developed by: Ashqar Ahamed S T
RegisterNumber: 212224240018
*/

import java.util.*;

class ListNode {
    int val;
    ListNode next;

    ListNode(int val) {
        this.val = val;
    }
}

class Solution {
    public ListNode removeElements(ListNode head, int val) {
        //Type your code here
        
        ListNode prev = null;
        ListNode temp = head;
        while(temp!=null)
        {
            if(temp.val == val && temp == head)
            {
                head = temp.next;
                temp = temp.next;
                continue;
            }
            if(temp.val == val)
            {
                prev.next = temp.next;
                temp = temp.next;
                continue;
            }
            prev = temp;
            temp = temp.next;
        }
        return head;
    }
}

public class Main {

    public static ListNode buildList(int[] arr) {
        if (arr.length == 0) return null;
        ListNode head = new ListNode(arr[0]);
        ListNode current = head;
        for (int i = 1; i < arr.length; i++) {
            current.next = new ListNode(arr[i]);
            current = current.next;
        }
        return head;
    }

    public static String listToString(ListNode head) {
        List<Integer> result = new ArrayList<>();
        while (head != null) {
            result.add(head.val);
            head = head.next;
        }
        return result.toString(); 
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

     
        String input = scanner.nextLine().replaceAll("\\s", "");
        int[] nums = Arrays.stream(input.split(",")).mapToInt(Integer::parseInt).toArray();

       
       
        int val = scanner.nextInt();

        ListNode head = buildList(nums);
        Solution solution = new Solution();
        ListNode updated = solution.removeElements(head, val);

        System.out.println(listToString(updated));

        scanner.close();
    }
}

```

## Output:

<img width="817" height="258" alt="output Day2" src="https://github.com/user-attachments/assets/217dae15-5641-484c-9a36-272009c60b96" />


## Result:
The java program successfully removes all nodes with the specified value (val) from the linked list and returns the new head.
