# Programming a Guessing Game
1에서 100 사이의 숫자 중 하나로 비밀번호를 생성하면 유저가 이를 추측하는 게임을 만들면서 Rust의 주요 개념들에 대해 알아보자.

## 추측 진행하기
```rust
use std::io;

fn main() {
    println!("Guess the number!");

    println!("Please input your guess.");

    let mut guess = String::new();

    io::stdin().read_line(&mut guess)
        .expect("Failed to read line");

    println!("You guessed: {}", guess);
}
```
- Rust는 기본적으로 모든 프로그램에 prelude의 몇 가지 타입을 가져온다. 만약 내가 사용하고 싶은 타입이 여기에 없을 경우 ```use``` 문을 통해 원하는 타입을 현재 스코프로 가져와야 한다.
- ```main``` 함수는 모든 프로그램의 시작점에서 호출된다. (```fn```: 함수 선언, ```()```: 파라미터 삽입, ```{}```: 함수의 시작과 끝)
- ```println!```는 매크로로 문자열을 화면에 프린트한다.

### 변수값 저장하기
```rust
let mut guess = String::new();
```
- Rust에서 변수 선언은 ```let```으로 할 수 있다. 기본적으로 변수값은 불변(immutable)이며, 가변(mutable)으로 하고 싶을 경우 변수 이름 앞에 ```mut```을 붙이면 된다.
- ```String::new();```는 새로운 빈 String 인스턴스를 생성한다.

```rust
io::stdin().read_line(&mut guess)
    .expect("Failed to read line");
```
- ```stdin``` 함수는 터미널에서 기본 input값을 처리하는 타입인 ```std::io::Stdin``` 인스턴스를 반환한다.
- ```read_line``` 함수는 argument로 String을 받는데, 이는 유저의 input값을 더해서 값이 바뀔 수 있으므로 가변적이어야 한다.
- input값 앞에 붙는 ```&```는 해당 argument가 (한번 데이터가 지정되면 코드 내에서 계속 사용되는) reference임을 의미한다. Reference는 기본적으로 불변이므로 뒤에 ```mut```을 붙임으로서 가변으로 바꿔준다.


### **```Result```** 타입으로 실패 가능성 막기

### **```println!```** placeholder로 값 프린트하기


## 비밀번호 생성하기

### Using a Crate to Get More Functionality

### Ensuring Reproducible Builds with the Cargo.lock File

### Updating a Crate to Get a New Version

### 임의의 숫자 생성하기


## 추측 숫자와 실제 비밀번호 비교하기

## 반복문을 통해 여러 숫자로 추측하기
### 정답을 맞추면 반복문 끝내기
### 잘못된 input handling
