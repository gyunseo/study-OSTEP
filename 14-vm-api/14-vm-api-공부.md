# 막간: 메모리 관리 API

- UNIX의 memory 관리 interface를 다룬다.
- 여기서 메모리 === 사용자 주소 공간

# 메모리 공간의 종류

- C Program이 실행되면, 2 가지 유형의 memory 공간이 할당 된다.

1. stack => 할당과 반환은 컴파일러에 의해 암묵적으로, automatic memory

- stack에 메모리를 선언하는 건 쉽다.

```c
void func() {
    int x; // stack에 int형을 선언
}
```

- 컴파일러가 알아서 func가 불리면 스택에 공간을 확보하고, ret하면 메모리를 반환

2. heap => 모든 할당과 반환이 프로그래머에 의해 명시적으로 처리

```c
void func() {
    int *x = (int *) malloc(sizeof(int));
}
```

- 코드 한 줄에서 스택과 힙 할당이 모두 발생
- 컴파일러가 포인터 변수`int *x`를 만나면, int 포인터를 위한 공간을 할당
- malloc()을 호출하여 int를 위한 공간을 힙으로부터 요구
