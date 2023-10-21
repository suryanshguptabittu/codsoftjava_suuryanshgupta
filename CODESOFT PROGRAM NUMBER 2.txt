import java.util.Scanner;
public class program2_codesoft {
    public static void main(String[] args) {
        // creating a Scanner class
        Scanner sc = new Scanner(System.in);
        System.out.println("                     GRADE STRUCTURE                   ");
        System.out.println("GRADE A -> 0.9+ SCORE");
        System.out.println("GRADE B -> 0.8 - 0.9 SCORE");
        System.out.println("GRADE C -> 0.6 - 0.7 SCORE");
        System.out.println("GRADE D -> BELOW 0.7 SCORE");
        System.out.println("FAIL -> 0.0 - 0.3 SCORE");
        System.out.println("Enter the marks obtained in Subject1 out of 100:");
        float sub1marks=sc.nextFloat();
        System.out.println("Enter the marks obtained in Subject2 out of 100:");
        float sub2marks=sc.nextFloat();
        System.out.println("Enter the marks obtained in Subject3 out of 100:");
        float sub3marks=sc.nextFloat();
        System.out.println("Enter the marks obtained in Subject4 out of 100:");
        float sub4marks=sc.nextFloat();
        System.out.println("Enter the marks obtained in Subject5 out of 100:");
        float sub5marks=sc.nextFloat();
        double sum=sub1marks+sub2marks+sub3marks+sub4marks+sub5marks;
        double avg_percentage=sum/500;
        if(avg_percentage>=0.9){
            System.out.println("GRADE A");
        }else if(avg_percentage>=0.8&&avg_percentage<0.9){
            System.out.println("GRADE B");
        }else if(avg_percentage>=0.7&&avg_percentage<0.8){
            System.out.println("GRADE C");
        }else if(avg_percentage<=0.7){
            System.out.println("GRADE D");
        }else if(avg_percentage>=0.0&&avg_percentage<=0.3){
            System.out.println("FAIL");
        }






    }
}
