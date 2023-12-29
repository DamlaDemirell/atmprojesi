# atmprojesi
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        String userName, password;
        Scanner input = new Scanner(System.in);
        int right = 3;
        int balance = 1500;
        int select;
        while (right > 0)
        {
            System.out.print ("Kullanıcı adınız: ");
            userName = input.nextLine();

            System.out.println("Şifreniz: ");
            password = input.nextLine();

            if(userName.equals("patika") && password.equals("dev123")){
                System.out.println("Merhaba, Kodluyoruz bankasına hoşgeldiniz.");
                do {
                    System.out.println("Lütfen yapmak istediğiniz işlemi seçiniz.");
                    System.out.println("" +
                            "1- Para yatır\n" +
                            "2-Para çekme \n" +
                            "3-Para durumunu sorgulama \n" +
                            "4-Çıkış yap");
                    select = input.nextInt();
                    if(select ==1 ){
                        System.out.println("Para miktarı: ");
                        int price = input.nextInt();
                        balance += price;
                    } else if (select==2){
                        System.out.println("Para miktarı: ");
                        int price = input.nextInt();
                        if (price > balance){
                            System.out.println("Bakiye yetersiz.");
                        }else {
                            balance -= price;
                        }
                    }else if (select==3){
                        System.out.println("Bakiyeniz: " + balance);
                    }
                } while (select != 4);
                break;
            } else {
                right--;
                System.out.println("Yanlış giriş yaptınız. Tekrar deneyiniz.");

                if (right ==0 ){
                    System.out.println("Hesabınız bloke olmuştur.Banka ile iletişime geçiniz.");
                } else {
                    System.out.println("Kalan hakkınız: " + right);
                }
                }


        }

    }
}
