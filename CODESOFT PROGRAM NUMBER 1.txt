import java.util.Random;
import java.util.Scanner;
class program1_codesoft{
    public static void main(String[] args) {
        //Creating a Scanner class
        Scanner sc = new Scanner(System.in);
        // Instance of the ranndom class
        Random rand = new Random();
        //setting the Upper bound
        int upperbound = 100;
        int randnum=rand.nextInt(upperbound);
//        System.out.println(randnum);
        int number_of_attempts_taken=0;
        int total_attemmpts=3;
        System.out.println("WELCOME USER,YOU HAVE MAX 3 ATTEMPTS TO GUESS THE CORRECT NUMBER");
        System.out.println("THE NUMBER ATTEMPTS YOU TAKE WILL BE DISPLAYED AT THE END WHEN YOU EITHER GUESS THE CORRECT NUMBER OR YOUR NUMBER OF ATTEMPTS ARE OVER");
        System.out.println("ENTER -1 IF YOU WANT TO START AGAIN FROM SCRATCH");
        for(int i=0;i<total_attemmpts;i++){
            System.out.println("Enter the Nummber you guessed");
            int guessnum=sc.nextInt();
            if(guessnum==randnum){
                System.out.println("congratulations,you have Entered the Correct Number");
                break;
            }else if(guessnum<randnum){
                System.out.println("The number you guessed is low");
                number_of_attempts_taken+=1;
            }else if(guessnum>randnum){
                System.out.println("The number you guessed is high");
                number_of_attempts_taken+=1;
            }else if(guessnum==-1){
                i=0;
                number_of_attempts_taken=0;
            }
            System.out.println("your total number of attempts are"+number_of_attempts_taken);
        }




    }
}
