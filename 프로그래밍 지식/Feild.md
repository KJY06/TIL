# Field

---

## 🪛 field

---

- **field**란 클래스 혹은 구조체에서 직접 **선언되는 모든 형식의 변수**다.
    - 클래스의 부품 역할을 하는 클래스의 내부 상태 값을 저장해놓는 그릇
- field는 인스턴스 필드, 정적 필드의 두가지가 있다.
- 일반적으로 필드는 **접근자가 private**이나 protected이다.
    - 왜냐하면 *캡슐화 때문*에 **개체의 데이터는 해당 개체에서만 접근 가능하게 해야하기 때문**이다.
- 필드의 형식
    - 변수 형식 : 평범한 변수이다.
    - **상수 형식** : const를 붙인 **변경 불가의 값**이다.
    - **읽기 전용 형식** : readonly를 붙인 **읽기만 가능**한 값이다.
    
    ```csharp
    using static System.Console;
    
    //readonly 예제.
    public class Program
    {
        private readonly int Count = 0;
        public static void Main()
        {
            Program pro = new Program();
    
            WriteLine(pro.Count);
    
            pro.Count++;//읽기 전용이라 값을 변경할 수 없다.
        }
    }
    ```
    
    - 배열 형식 : 평범한 배열 변수이다.