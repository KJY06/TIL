# static / final

---

## 📌 Static

---

- static은 **변수나 메서드의 키워드**로 사용된다.
- static을 사용하는 이유는 변하지 않는 값 때문에 생기는 불필요한 메모리 낭비를 막기 위해서다.
- 변하지 않고 고정적으로 사용되기에 정적이다.

```csharp
using static System.Console;

class SharpDemo
{
    public string name = "김진영";
}

public class MainClass
{
    public static void Main()
    {
        SharpDemo demo = new SharpDemo();
        WriteLine(demo.name);
    }
}
```

- 이 코드는 우리가 흔히 아는 인스턴스를 통한 접근이다.
- **인스턴스는 매번 생성할 때 마다 메모리가 별도로 할당된다.**

```csharp
using static System.Console;

class SharpDemo
{
    public static string name = "김진영";
}

public class MainClass
{
    public static void Main()
    {
        WriteLine(SharpDemo.name);
    }
}
```

- 변하지 않는 값이라면 static을 이용하면 효율적이다. static은 객체 선언 즉시 메모리를 할당받기에 반복적으로 **생성해도 메모리 크기가 유지된다.**
- static 키워드는 해당 메서드를 공유시키는 키워드이다. 즉 **전역변수와 개념이 비슷하다.**
- C#에선 static을 선언할 땐 객체를 생성하지 않고, **[클래스명.메서드명]** 형식으로 호출한다. 또한 static은 인스턴스로 호출될 수 없다.

## 🏠 static 클래스

---

- static 클래스는 **모든 멤버가 static으로 되어있다.**
- static 클래스는 객체를 생성할 수 없기 때문에 public 생성자를 가질 수 없지만 static 생성자를 가질 순 있다.
    - static 생성자는 주로 static 필드를 초기화 할 때 사용된다.
    - static 생성자는 엑세스 한정자와 매개변수를 가질 수 없다.

## 👍 장,단점

---

- 장점
    - 프로그램 종료까지 static 멤버로 인한 메모리 변경이 없다.
    - **멤버에 직접 접근이 가능**해 편리하다.
- 단점
    - 참조하는 곳이 많을 수록 **객체 지향의 개념과 멀어지게 된다.**

## 🚫 final

---

- 일단 **C#엔 final이 없다**는 것을 말해둔다.
- final은 **변수, 메서드, 클래스에 붙을 수 있다.**
- 변수
    - 변수에 final을 붙이면 **수정할 수 없음**을 의미한다.
    - 다만 그 **범위는 그 변수의 값에 한정**된다. 따라서 참조형 변수로 받아온다면 다른 방법으로 충분히 값을 바꿀 수 있다.
    - 무조건 변수 사용 전에 초기화를 해줘야 한다.
- 메서드
    - 메서드에 final을 붙이면 **오버라이드를 제한**하게 된다.
    - 상속 받은 클래스에서 해당 **메서드를 재정의해서 사용하지 못하도록** 할 수 있다.
- 클래스
    - 반면 클래스에 final을 붙이면 아예 **상속이 불가능**하게 된다.
    - 재정의의 필요가 없을 경우 final로 선언하면 추후 유지보수가 편하다.