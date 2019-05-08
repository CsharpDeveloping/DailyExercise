//It is a single demo for ID-card judge.
import java.text.SimpleDateFormat;
import java.util.Scanner;

public class Program{
    public static int[]num={7,9,10,5,8,4,2,1,6,3,7,9,10,5,8,4,2};
    public static char[]jd={'1','0','X','9','8','7','6','5','4','3','2'};
    public static boolean is18(String string)
    {
        return string.length()==18;
    }
    public static boolean isnum(String str)
    {
        for (int i = 0; i < str.length()-1; i++)
            if(!Character.isDigit(str.charAt(i)))
                return  false;
        return true;
    }
    public static boolean last(String str)
    {
        char ch=str.charAt(str.length()-1);
        if(Character.isDigit(ch))
            return true;
        else if(Character.toLowerCase(ch)=='x')
            return true;
        else
            return false;
    }
    public static boolean date(String str)
    {
        SimpleDateFormat sd=new SimpleDateFormat("yyyyMMdd");
        try {
            sd.setLenient(false);
            sd.parse(str.substring(6,14));
        }
        catch (Exception e)
        {
            return false;
        }
        return true;
    }
    public static void print(String str)
    {
        System.out.println(str.substring(6,10)+"-"+str.substring(10,12)+"-"+str.substring(12,14));
    }
    public static boolean judge(String str)
    {
        int sum=0;
        for (int i = 0; i < str.length()-1; i++) {
          //  System.out.println(Integer.parseInt(str.charAt(i)+""));
            sum+=Integer.parseInt(str.charAt(i)+"")*num[i];
        }
        sum%=11;
        //System.out.println(jd[sum]);
        if(sum==2)
        {
            return Character.toLowerCase(jd[sum])== Character.toLowerCase(str.charAt(str.length()-1));
        }
        else
            return jd[sum]==str.charAt(str.length()-1);
    }
    public static boolean Judge(String str)
    {
        /*
        System.out.println(is18(str));
        System.out.println(last(str));
        System.out.println(date(str));
        System.out.println(judge(str));
        */
        return  is18(str)&&last(str)&&date(str)&&judge(str);
    }
    public static void main(String[] args)  {
        Scanner sc=new Scanner(System.in);
        String str=sc.nextLine();
        if(Judge(str))
        {
            print(str);
        }
        else
        {
            System.out.println("0000-00-00");
        }
        sc.close();
    }
}
