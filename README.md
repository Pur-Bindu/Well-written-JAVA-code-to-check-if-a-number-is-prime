package testPackage;

import java.util.InputMismatchException;
import java.util.Scanner;

public class CheckForPrime {

	private static Scanner reader;
	private static int number;

	public static void main(String[] args) {
		
		reader= new Scanner(System.in);
		System.out.println("Enter a number for check:");
		
		try
		{
			//capture the input in an integer
			number=reader.nextInt();
		} //End Try
		catch (InputMismatchException exception) 
		{ 
		    System.out.println("Please provide an integer value only"); 
		    System.exit(0);
		} //End Catch
		
		//If ifPrime is true then the number is prime else not
		if(ifPrime(number))
		{
			System.out.println(number + " is a Prime Number");
		}
		else
		{
			System.out.println(number + " is not a Prime Number");
		}
		
	} //End main
	
	/**
	 * Function to check if a number is prime number
	 */
	private static boolean ifPrime(int number)
	{
		boolean isPrime = true;
		
		//check if number is a multiple of 2
	    if (number%2 == 0) 
	    {
	    	isPrime = false;
	    }//End If
	    else
	    {
	    	//if not, then just check for the possibility of the number not being prime
		    for(int i=3;i*i<=number;i+=2) 
		    {
		    	if(number%i == 0)
		    	{
		    		isPrime = false;
		    	}//End If
		    	
		    }//End For

	   }//End Else
	
	   return isPrime;
	   
	} //End ifPrime

} //End class
