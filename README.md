# assignment1
assignment 1 of SMD


package assignment1;


import java.util.Scanner;
interface addinterface
{
	public void add(int a,int b);
}
interface subinterface
{
	public void sub(int a,int b);
}
interface mulinterface
{
	public void mul(int a,int b);
}
interface divinterface
{
	public void div(int a,int b);
}

class addclass implements addinterface
{
	public void add(int a,int b)
	{
		int result  =  a+b;
		System.out.println(result);
	}
}
class subclass implements subinterface
{
	public void sub(int a,int b)
	{
		int result  =  a-b;
		System.out.println(result);
	}
}
class mulclass implements mulinterface
{
	public void mul(int a,int b)
	{
		int result  =  a*b;
		System.out.println(result);
	}
}
class divclass implements divinterface
{
	public void div(int a,int b)
	{
            
            try
            {
                int result  =  a/b;
		System.out.println(result);
            
            }
            catch(ArithmeticException e)
            {
                System.out.println ("You Shouldn't divide a number by zero");
            }
		
	}
}
 abstract class properties
{
    private static int digits=14;
    private static String color="blcak";
    abstract void size();
    //static mehods
    static void color()
    {
        System.out.printf("%nThe color is ");
        System.out.printf( color);
    }
    static void digits()
    {
        System.out.printf("%nThe total digits of calculator are ");
        System.out.println( digits);
    }
    
    
}
  class calculator extends properties implements addinterface,subinterface,mulinterface,divinterface 
  {
  
		public void add(int a,int b)
		{
                    
			addclass ins  =  new addclass();
			ins.add(a, b);
                        
		}
		public void sub(int a,int b)
		{
                   
			subclass ins  =  new subclass();
			ins.sub(a, b);
                        
		}
	
		public void mul(int a,int b)
		{
                    
			mulclass ins  =  new mulclass();
			ins.mul(a, b);
                        
		}
	
		public void div(int a,int b)
		{
                        divclass ins  =  new divclass();
			ins.div(a, b);
                        
		}
                @Override
                public void size()
                {
        
                    System.out.printf("%nCalculator is of small size");
                }
}
    
public class Assignment1 
{
    
    
    public static void main(String[] args) 
    {
        calculator ins  =  new calculator();
	calculator.color();
        calculator.digits();
        System.out.println("Enter numbers to add");
        Scanner Input1 = new Scanner(System.in);
        String variable = Input1.next();
        Scanner Input2 = new Scanner(System.in);
        String variable2 = Input2.next();
        
        try
        {
            int aa = Integer.parseInt(variable);
            int bb = Integer.parseInt(variable2);
            System.out.println("a)addition%nb)subtraction%nc)multiplication%nd)division");
            Scanner Input3 = new Scanner(System.in);
            String variable3 = Input1.next();
            if("a".equals(variable3))
            {
                ins.add(aa, bb);
            }
            else if("b".equals(variable3))
            {
                ins.sub(aa, bb);
            }
            else if("c".equals(variable3))
            {
                ins.mul(aa, bb);
            }
            else if("d".equals(variable3))
            {
                ins.div(aa, bb);
            }
            
            
            
            
        }
        catch(NumberFormatException e)
        {
            System.out.println("Number format exception occurred");
            System.exit(0);
        }
       
        
        
        
        
        
        
        
        
        
        
    }
    
}
