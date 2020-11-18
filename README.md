import java.util.*;

public class EXERCISE {
	public static void main(String[] args) {
		
	Scanner input = new Scanner(System.in);
	
	System.out.println("please enter password : ");
	String passWord = input.nextLine();	
	System.out.println(isValid(passWord));
	}
	
	public static boolean isValid(String passWord) {
		boolean test =  hasEightChar(passWord) && hasOnlyLettersAndDigits(passWord) &&  hasAtleastTowDigit(passWord);
		return test;
	}
	public static boolean hasEightChar(String passWord) {
		
			if(passWord.length() < 8) {
				return false;
				}
			else {
				return true;
				}
	}
	public static boolean hasOnlyLettersAndDigits(String passWord) {
		int count = 0;
		boolean result = false||true;
		boolean isdigit = false;
		boolean isletter = false;
		
		for(int i=1;i<=passWord.length();i++) {
			char ch = passWord.charAt(count);
			    isdigit = Character.isDigit(ch);
			    isletter = Character.isLetter(ch);
			         if(isdigit || isletter) {
			    	     count++;
			    	     }
			         else {return false;}	
		}
		return result;
	}
	public static boolean hasAtleastTowDigit(String passWord) {
		int count = 0;
		int counts = 0;
		
		for(int i=0;i<passWord.length();i++) {
			char ch = passWord.charAt(i);
			  if(Character.isDigit(ch)) {
				  count++;
				}
			
		if(Character.isLetter(ch)) {
			counts++;
			}
		}
	  return count >= 2 ;
	}
}
