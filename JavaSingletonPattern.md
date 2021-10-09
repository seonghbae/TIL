# Java 싱글톤 패턴
```java
/**
 * Singleton pattern 예제
 */

class Card{
    private int cardNumber;
    private static int serialNum = 10000;   // 여러 객체가 공유하는 변수
    
    // 생성자
    Card(){
        serialNum++;    // 카드 생성 시마다 새로운 시리얼 넘버
        this.cardNumber = serialNum;    // static의 경우 this 사용 불가
    }
    
    // getCardNumber()로 private 변수 cardNumber에 접근
    public int getCardNumber(){
        return this.cardNumber;
    }
    
    public void setCardNumber(int cardNumber){
        this.cardNumber = cardNumber;  
    }
}

/**
 * Singleton pattern 정석 예제
 */
class CardCompany{
    private static CardCompany instance = new CardCompany();    // 여러 객체가 공유하는 인스턴스(단 하나만 존재->싱글톤)
    
    private CardCompany() {}    // 생성자 : 객체 생성 시 private로 생성해서 getInstance()로만 접근
    
    public static CardCompany getInstance(){
        if(instance==null) {    // instance가 존재하지 않는 경우 생성
            instance = new CardCompany();
        }
        return instance;
    }
    
    public Card createCard(){
        Card card = new Card();
        return card;
    }
}

public class CardCompanyTest {
    public static void main(String args[]) {
      
      CardCompany company = CardCompany.getInstance();  // 싱글톤 패턴
      
      Card myCard = company.createCard();   // 메서드에서 Card 생성
      Card yourCard = company.createCard();
      
      System.out.println(myCard.getCardNumber());   // 10001 출력
      System.out.println(yourCard.getCardNumber());   // 10002 출력
    }
}
```
- 출처(여러 가지 있으니 더 공부할 것) : https://webdevtechblog.com/%EC%8B%B1%EA%B8%80%ED%84%B4-%ED%8C%A8%ED%84%B4-singleton-pattern-db75ed29c36