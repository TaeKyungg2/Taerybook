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
let maybe=Some(10)

if let Some(x) = maybe {print!("{x}")} //10
else {println!("매칭실패");}
```

let 은 할당한다! 이고, if let 은 타입이 맞으면 할당한다! 이다.\
그리고 할당한 후에, 뒤의 { }를 실행하고, 타입이 안 맞으면 { } 를 실행한다.

정말 직관적인 문법이지만, 적응은 필요한 것 같다.&#x20;

### &#x20;`while let`

```rust
let x=Some(10)
while let Some(t)=x {
    print!("{}", t); //10
}
```

t 와 x 의 타입이 같으면 let's binding 후 { } 를 반복한다. 타입만 같으면 계속..

## `let else`&#x20;

```rust
let Some(x)=y else{ print!("not match");}
```

매칭이 안되면 { } 실행한다.
