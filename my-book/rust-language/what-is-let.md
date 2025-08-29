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

그냥 변수 할당만 하지 않고, rust 에는 특별하고 유용한 문법들이 있다.

## &#x20;`if let`

```rust
let maybe:i32 = 10;
let x:i32;

if let x = maybe {print!("{x}")} //10
else {println!("매칭실패");}
```

let 은 할당한다! 이고, if let 은 타입이 맞으면 할당한다! 이다.\
그리고 할당한 후에, 뒤의 { }를 실행하고, 타입이 안 맞으면 { } 를 실행한다.

정말 직관적인 문법이지만, 적응은 필요한 것 같다.&#x20;

### &#x20;`while let`

```rust
let x:i32=10;
let t:i32;
while let t=x {
    print!("{}", x); //10
}
```

t 와 x 의 타입이 같으면 let's binding 후 { } 를 반복한다.&#x20;

이 예시에서는 타입이 i32 라서 타입이 안 바뀌는데, enum 같은 것들은 바뀔 수 있으므로 그때 쓸 것 같다.\


## `let else`&#x20;

```rust
let x:i32=0.9 else{ print!("not match");}
```

매칭이 안되면 { } 실행한다.
