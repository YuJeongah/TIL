# Apr-14  TIL

### 

### 조별 워크샵 진행

주로 if문 while문 배열을 이용한 문제를 생성함

NumberGuessGame을 주제로 잡고

상세한 시나리오를 구상함

우리 조가 구상한 코드는 아래와 같다.

package tw;

import java.util.Random;
import java.util.Scanner;

public class Ws01 {

	public static void main(String[] args) {
		Random r = new Random();
		Scanner sc = new Scanner(System.in);
		System.out.println("Game Start...");
		int a = r.nextInt(10)+1;
		int cnt = 5;
		while(true) {



			System.out.println("1~10숫자를 입력하세요.");
			String num = sc.next();
			if(num.contentEquals("종료")) {
				sc.close();
				System.out.println("종료");
				break;
			}
			int n = Integer.parseInt(num);
			if (n <0 || n>10) {
				System.out.println("입력오류");
				continue;
			}
			if(n>a) {
				System.out.println("down");
				cnt--;
				
			}else if(n<a){
				System.out.println("up");
				cnt--;
			}else if(n == a) {
				sc.close();
				System.out.println("정답");
				return;
			}
			if(cnt == 0) {
				System.out.println("정답은 :" +a+" 끝\n");
				a = r.nextInt(10)+1;
				cnt = 5;
				continue;
			}
		}
		
	}
}