# Rotate-Array
Sample Input 0

7 3

1 2 3 4 5 6 7

Sample Output 0

5 6 7 1 2 3 4

Explanation

rotate 1 steps to the right: [7, 1, 2, 3, 4, 5, 6]
rotate 2 steps to the right: [6, 7, 1, 2, 3, 4, 5]
rotate 3 steps to the right: [5, 6, 7, 1, 2, 3, 4].
Example
Input
7 3
1 2 3 4 5 6 7
Output
5 6 7 1 2 3 4


/* package codechef; // don't place package name! */
import java.util.*;
import java.lang.*;
import java.io.*;

/* Name of the class has to be "Main" only if the class is public. */
public class Main
{
    public static void main (String[] args) throws java.lang.Exception
    {
        // your code goes here
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		int[] arr = new int[n];
		int k = sc.nextInt();
		for(int i = 0;i<n;i++){
			arr[i] = sc.nextInt(); 
		}
		
		k = k%n;
		if(k==0){
			for(int arr1:arr){
				System.out.print(arr1+" ");
			}
			return;
		}
		int temp , start , end;
		start = n-k;
		end = n-1;
		while(start<end){
			temp = arr[start];
			arr[start]=arr[end];
			arr[end]=temp;
			start++;
			end--;
		}
		start = 0;
		end = (n-k)-1;
		while(start < end){
			temp = arr[start];
			arr[start]=arr[end];
			arr[end]=temp;
			start++;
			end--;
		}
		start = 0;
		end = n-1;
		while(start<end){
			temp=arr[start];
			arr[start]=arr[end];
			arr[end]=temp;
			start++;
			end--;
		}
		for(int arr1:arr){
			System.out.print(arr1+" ");
		}
    }
}
