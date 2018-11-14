//Roneil Harris
//10/5/2018
//Assignment4: Binary Search

import java.util.Scanner;
class Assignment3
{
	static Scanner kb = new Scanner(System.in);
	
	public static void main(String[] args)
	{
		int n, low = 1, high = 1000000;
		
		System.out.println("Think of a number between 1 and 1000000. Enter it below");
		n = kb.nextInt();
		
		if((n < low) || (n > high))
			System.out.println("Error:number outside of range");
		else
			System.out.println("The number you picked is: " + guess(low,high,n));
		
	}
	public static int guess(int low, int high, int n)
	{	
		int midpoint = 0;
		String response;
		
		if(low == high)
			return low; 	//return either low or high, since they are the same
		
		if(n == low)
			return low;
		
		else if(n == high)
			return high;
						
		midpoint = (low + high)/2;
		System.out.println("The midpoint is " + midpoint);
			
		if(midpoint == n)
			return midpoint;
		
		System.out.println("Is your number larger than  midpoint?");
		
		response = kb.next();
		
		if(response.equals("yes"))
		{
			low = midpoint + 1;
			return guess(low, high, n);
		}
		
		else
		{
			high = midpoint - 1;
			return guess(low, high, n);
		}
	}
}