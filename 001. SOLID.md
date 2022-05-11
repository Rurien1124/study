- ## 1. SOLID
  - SRP : 하나의 클래스는 하나의 책임만을 가져야 한다
    - 적용 전
    ```
    public class Snack {
      private String name;
      private String taste;
      private int calories;
      private List<String> ingredients;
      
      public getName() {...}
    }
    ```
    
    - 적용 후
    ```
    public class Snack {
      private String name;
      private SnackInfo snackInfo;
      
      public getName() {...}
    }
    
    public class SnackInfo {
      private String manufacturer;
      private String taste;
      private int calories;
      private List<String> ingredients;
    }
    ```
    
  - OCP : 확장되거나 변경되어야 하는 부분을 추상화하여 변경이 쉽도록 한다
    - 적용 전
    ```
    public class ChocoPie {...}
    public class ChocoPieInfo {...}
    public class GhanaPie {...}
    public class GhanaPieInfo {...}
    ```
    - 적용 후
    ```
    public class Pie {
      protected String name;
    }
    
    public class PieInfo {
      protected String manufacturer;
      protected String taste;
      protected int calories;
      protected List<String> ingredients;
    }
    
    public class ChocoPie extends Pie {
      public ChocoPie(String name) {...}
    }
    
    public class ChocoPieInfo extends PieInfo {
      public ChocoPieInfo(String manufacturer, String taste, int calories, List<String> ingredients) {...}
    }
    
    public class GhanaPie extends Pie {
      public GhanaPie(String name) {...}
    }
    
    public class GhanaPieInfo extends PieInfo {
      public ChocoPieInfo(String manufacturer, String taste, int calories, List<String> ingredients) {...}
    }
    ```
    
  - LSP : 클래스 B가 클래스 A의 하위 클래스라면, 클래스 A의 객체를 클래스 B의 객체로 치환할 수 있어야 한다.
          자식 클래스는 부모 클래스의 역할을 **포함**해야한다.
  ```
  public class 직사각형 {
    protected int 높이;
    protected int 너비;
    
    public int set높이(int 높이) {...}
    public int set너비(int 너비) {...}
    public int get높이() {...}
    public int get너비() {...}
    
    public int getArea() {return this.높이 * this.너비;}
  }
  
  public class 정사각형 extends 직사각형 {
    @Override
    public void set높이(int 높이) {
      this.높이 = **높이**;
      this.너비 = **높이**;
    }
    
    @Override
    public void set너비(int 너비) {
      this.높이 = **너비**;
      this.너비 = **너비**;
    }
  }
  
  public static void main(String[] args) {
    직사각형 rectangle = new 직사각형();
    rectangle.set높이(2);
    rectangle.set너비(3);
    
    // 직사각형은 테스트 통과
    assertThat(rectangle.getArea()).isEqualTo(6);
    
    직사각형 square = new 정사각형();
    square.set높이(2);
    square.set너비(3);
    
    // 직사각형을 상속받은 정사각형은 테스트 통과 불가능
    assertThat(rectangle.getArea()).isEqualTo(6);
  }
  
  // 따라서, 정사각형의 상속을 제거하거나, getArea()함수를 정사각형에도 추가해주어야 함
  ```
  
  - ISP : 인터페이스를 분리해서 특정한 기능만 쓸 수 있도록
  - DIP : 저수준 모듈들을 인터페이스로 분리해서 고수준 모듈이 저수준 모듈에 의존하지 않도록
