# ZOHO_Questions
### Sort in specific order
[Geeksfor geeks link](https://www.geeksforgeeks.org/problems/sort-in-specific-order2422/1)
<br>
Given an array arr[] of positive integers. Your task is to sort them so that the first part of the array contains odd numbers sorted in descending order, and the rest of the portion contains even numbers sorted in ascending order.

Examples:
Input: arr[] = [1, 2, 3, 5, 4, 7, 10]
Output: [7, 5, 3, 1, 2, 4, 10]
Explanation: 7 5 3 1 are odds in descending order and 2 4 10 are evens in ascending order.

Input: arr[] = [0, 4, 5, 3, 7, 2, 1]
Output: [7, 5, 3, 1, 0, 2, 4]
Explanation: 7 5 3 1 are odds in descending order and 0 2 4 are evens in ascending order.
Expected Time Complexity:  O(nlog(n))
Expected Auxiliary Space:  O(1)

```java
class Solution {
    public void sortIt(Long arr[]) {
        int i = 0,j = arr.length-1;
        while(i<=j)
        {
            if(arr[i]%2==0 && arr[j]%2!=0) 
            {
                long t=arr[i];
                arr[i]=-arr[j];
                arr[j]=t;
                i++;
                j--;
            }
            else if(arr[i]%2!=0) 
            {
                arr[i]=-arr[i];
                i++;
            }
            else if(arr[j]%2==0) j--;
        }
        Arrays.sort(arr);
        for(int k=0;k<i;k++) arr[k]=-arr[k];
    }
}
```
- In this code we separate the odd and even numbers and odd numbers are in first and even numbers are in last.
- And the first odd numbers are in desending order and the last even numbers are in asending order.
- The idea is first we multiply the odd numbers by -1. Then the numbers are changed into negative numbers.
- We know if we sort the negative nubers the bigger one come first.
- that is -3 -2 -7 after sorting the number -7 -3 -2 then we remove the negative sign then it will like desending order 7 3 2
- This will workout in this problem that is first we convert  all the odd numbers into negative form because we sort all the oddnumbers by desending order.
- Then we sort the array the odd numbers are sort in asending order and come in front.
- After sorting the array we change the negative sign to positive sign.
> [Reference](https://www.youtube.com/watch?v=73jFBYeguzU)
