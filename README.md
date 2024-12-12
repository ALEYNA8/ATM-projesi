# ATM-projesi
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
       String userName, password;
       Scanner input = new Scanner(System.in);
       int right = 3;
       int balance = 1500;

       while (right > 0) {
           System.out.print("Kullanıcı adınız: ");
           userName = input.nextLine();
           System.out.print("Parolanız: ");
           password = input.nextLine();

           if (userName.equals("patika") && password.equals("dev123")) {
               System.out.println("Merhaba, Kodluyoruz Bankasına Hoşgeldiniz!");
               int select;

               do {
                   System.out.println("1-Para yatırma");
                   System.out.println("2-Para çekme");
                   System.out.println("3-Bakiye sorgula");
                   System.out.println("4-Çıkış yap");
                   System.out.print("Lütfen yapmak istediğiniz işlemi seçiniz: ");
                   select = input.nextInt();

                   switch (select) {
                       case 1:
                           System.out.print("Pra miktarı: ");
                           int deposit = input.nextInt();
                           balance += deposit;
                           System.out.println("Bakiyeniz: " + balance);
                           break;

                       case 2:
                           System.out.print("Para miktarı: ");
                           int withdraw = input.nextInt();
                           if (withdraw > balance) {
                               System.out.println("Bakiye yetersiz: ");
                           }else {
                               balance -= withdraw;
                               System.out.println("Kalan bakiyeniz: " + balance);
                           }
                           break;
                       case 3:
                           System.out.println("Bakiyeniz: " + balance);
                           break;
                       case 4:
                           System.out.println("Tekrar görüşmek üzere: ");
                           break;
                       default:
                           System.out.println("Geçersiz işlem. Lütfen tekrar deneyiniz.");
                   }
               }while (select != 4);
               break;
           }else {
               right--;
               System.out.println("Hatalı kullanıcı adı veya şifre. Tekrar deneyiniz.");
               if (right == 0) {
                   System.out.println("Hesabınız bloke olmuştur lütfen banka ile iletişime geçiniz.");
               }else {
                   System.out.println("Kalan Hakkınız: " + right);
               }
           }
       }
       input.close();
    }
}
