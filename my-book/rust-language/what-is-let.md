# What is "Let"

rust 에서 let 키워드가 많이 나온다.

```rust
fn main(){
    let x=9
    let l="hello"
}
```

변수 선언을 let 으로 한다.&#x20;

> let's x는 9이다!
>
> let's l 은 "hello" 이다!

이런 뜻이라고 한다. 이걸 용어로 말하면 "binding" 이라고 한다.

그냥 변수 할당하는 건데, rust 에는 특별하고 유용한 문법들이 있다.

## &#x20;`if let`

```rust
let maybe:i32 = 10;
let x:i32;

if let x = maybe {print!("{x}") //10} 
else {
    println!("매칭실패");
}
```

let 은 할당한다! 이고, if let 은 타입이 맞으면 할당한다! 이다.\
그리고 할당한 후에, 뒤의 { }를 실행하고, 타입이 안 맞으면 { } 를 실행한다.

정말 직관적인 문법이지만, 적응은 필요한 것 같다.&#x20;

***

### &#x20;`while let`

```rust
let x:i32;
let t:i32;
while let Some(x) = v.pop() {
    println!("{}", x);
}
// 출력: 3, 2, 1
```

***

### 4. `let else`&#x20;

**매칭 실패하면 바로 else 블록 실행**\
(특히 함수 초반 "검증 → 실패시 빠른 반환"에 유용)

```rust
fn get_number(opt: Option<i32>) -> i32 {
    let Some(v) = opt else {
        return 0; // None이면 여기서 조기 반환
    };
    v * 2
}

fn main() {
    println!("{}", get_number(Some(10))); // 20
    println!("{}", get_number(None));     // 0
}
```

***
