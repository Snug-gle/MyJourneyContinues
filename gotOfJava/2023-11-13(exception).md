##### There is no rule has no exception
- 자바에서는 예상을 했든, 예상을 하지 않았건 예외적인 일이 발생하게 되면 "예외"를 던져버림

```java
package c.exception;  
  
public class ExceptionSample {  
  
  public static void main(String[] args) {  
    ExceptionSample sample = new ExceptionSample();  
    sample.arrayOutOfBounds();  
  }  
  
  private void arrayOutOfBounds() {  
    try {  
      int[] intArray = new int[5];  
      System.out.println(intArray[5]);  
      System.out.println("This code should run.");  
    } catch (Exception e) {  
      System.err.println("Exception occured"); // err를 사용 시, IDE에서는 출력결과가 다른 색으로 표시됨
    }  
    System.out.println("This code must run.");  
  }  
}
```
##### try-catch 블록 내 변수선언
- try 블록은 중괄호로 쌓여 있는 블록 -> 블록 내에 선언한 변수를 catch에서 사용할 수 없음
- catch 문장에서 사용할 변수에 대해서는 try 앞에 미리 선언해 놓는다.
##### 두 개 이상의 catch

