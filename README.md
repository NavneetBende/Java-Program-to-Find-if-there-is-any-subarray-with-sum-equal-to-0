Subarray with sum equal to Zero in Java
Here, in this page we will discuss the program to find if there is any subarray with sum equal to zero in C++ programming language. If such subarray is present then print true otherwise print false.

Java Program to Find if there is any subarray with sum equal to 0
Method 1 :
Run a outer loop for index 0 to n.
Run a nested loop from index i+1 to n,
Find sum, if it is equal to 0, then print true.
Otherwise, print false.
Method 1 : Code in Java
Run
import java.util.HashSet;
import java.util.Set;
public class Main
{ static Boolean subArrayExists(int arr[])
    {
        // Creates an empty hashset hs
        Set hs = new HashSet();
        // Initialize sum of elements
        int sum = 0;
 
        // Traverse through the given array
        for (int i = 0; i < arr.length; i++)
        {
            // Add current element to sum
            sum += arr[i];
            if (arr[i] == 0 || sum == 0 || hs.contains(sum))
                return true;

            // Add sum to hash set
            hs.add(sum);
        }

        // We reach here only when there is
        // no subarray with 0 sum
        return false;
    }

    // Driver code
    public static void main(String arg[])
    {
        int arr[] = { -3, 3, 1, 6 };
        if (subArrayExists(arr))
            System.out.println(
                "Found a subarray with 0 sum");
        else
            System.out.println("No Such Sub Array Exists!");
    }
}
Output
Found a subarray with 0 sum
