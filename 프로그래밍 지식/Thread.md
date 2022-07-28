# Thread

---

## ❓ 스레드와 프로세스

---

- 프로세스 : 프로그램이 메모리에 올라갔을 때의 상태.
- **스레드** : 프로그램에서 순차적으로 실행하는 **실행 흐름, 단위**
- 스레드는 기본적으로 프로세스당 1개만 존재하지만 더 추가하면 여러 곳을 동시에 동작하게 할 수 있다.

## 스레드 생성

---

```csharp
using System;
using System.Threading; //스레드를 생성하기 위한 네임스페이스.
 
class Program {
    public static void Foo() {
        Console.WriteLine("Foo Start");
        Thread.Sleep(2000);
        Console.WriteLine("Foo End");
    }
    
    public static void Main() {
        **Thread t = new Thread(Program.Foo);
        t.Start(); //스레드 생성과 실행 명령어.**
        
        Console.WriteLine("Main Start");
        Thread.Sleep(2000);
        Console.WriteLine("Main End");
    }
}
```

- 이 코드의 실행 결과는 아래와 같다.
    
    Main Start → Foo Start → 2초 대기 → Main End → Foo End
    
- 즉 **Main과 Foo가 동시에 실행**됬고 이는 다른 말로 **스레드가 2개**라는 뜻이다.