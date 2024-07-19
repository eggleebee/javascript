# 02-함수
# 02-04-함수 선언식과 함수 표현식
# 02-04-01 함수 표현식

## 리터럴(literal)
+ 리터럴은 사람이 이해할 수 있는 문자 또는 약속된 기호를 사용해 값을 생성하는 표기방식을 말한다.
+ 즉, 리터럴은 값을 생성하기 위한 표기법이다.

````
<script>
    let age = 10;
    let name ="홍길동";
    let bool = true;

    let arr = ["포도","딸기"]; // 배열 리터럴
    {} // 객체 리터럴
    function () {} // 함수 리터럴
</script>
````

## 함수 리터럴(function literal)
+ 자바스크립트에서는 함수도 데이터이므로 변수에 함수를 대입하고, 다른 함수의 인수로 전달하고, 반환값으로 함수를 건네주는 것이 가능하다.

````
<script>
    // 변수에 함수리터럴 할당
    const add = function add(x, y) {
        return x + y;
    }
    console.log(add(2, 5));
</script>
````

## 식(expression)
+ 식(expression)이란 값을 만들어내는 코드 단위이다. 
+ 표현식(Expression)은 하나의 값으로 평가(Evaluation)된다. 무엇이든 하나의 값(value)를 반환하는 것은 식이다. 
+ 값(리터럴), 변수, 객체의 프로퍼티, 배열의 요소, 함수 호출, 메소드 호출, 피연산자와 연산자의 조합은 모두 표현식이며 하나의 값으로 평가(Evaluation)된다. 
+ 표현식은 결국 하나의 값이 되기 때문에 다른 표현식의 일부가 되어 조금 더 복잡한 표현식을 구성할 수도 있다.

````
<script>
    100 ; // 숫자 리터럴
    "Hi"; // 문자 리터럴
    true; // 불린 리터럴

    "Hello" + "World"; // 문자식 

    // 연산식 : 산술식, 논리식
    1 + 4; // 5 
    1 * 2 * 3 > 1 // true
    true || 1 // true
    10 < 100; // true
    (5 * 10 > 10) && (5 * 10 < 100)  // true

    // 할당식
    x = 100;  
    score = 50 + 50;
</script>
````

## 문(Statement)
+ 문(statement)은 어떤 작업을 수행하는 코드 단위다. (변수 선언문, 할당문, 함수 선언문, 조건문, 반복문)
+ 문은 var, function과 같은 선언 키워드를 사용하여 변수나 함수를 생성하기도 하고
+ if, for, while 문과 같은 제어문을 생성하여 프로그램의 흐름을 제어하기도 한다.
+ 표현식을 통해 평가된 값을 실제로 컴퓨터에게 명령을 하여 무언가를 하는 것은 문이다.
+ 문의 집합으로 이루어진 것이 바로 프로그램이며, 문을 작성하고 순서에 맞게 나열하는 것이 프로그래밍이다. 문을 명령문이라고도 부른다.
+ 문은 리터럴, 연산자(Operator), 표현식(Expression), 키워드(Keyword) 등으로 구성되며 세미클론(;)으로 끝나야 한다.
+ 문은 코드 블록 {중괄호})으로 그룹화할 수 있다. 그룹화의 목적은 함께 실행되어져야 하는 문을 정의하기 위함이다.
+ 문들은 일반적으로 위에서 순서대로 실행된다. 
+ 이러한 실행 순서는 조건문(if, switch)이나 반복문(while, for)의 사용으로 제어할 수 있다. 이를 흐름제어(Control Flow)라 한다. 
+ 또는 함수 호출로 변경될 수 있다.

````
<script>
    // 변수 선언문
    let x;

    // 할당문
    x = 5;

    // 함수 선언문
    function foo(x, y) {
	    return x + y;
    }

    // 조건문
    if (x > 1) {
        console.log(x);
    }

    // 반복문
    for (let i = 0; i < 2; i++) {
        console.log(i);
    }
</script>
````

````
<script>
    let time = 0;
    let greeting;

    if (time < 10) {
        greeting = 'Good morning';
    } else if (time < 20) {
        greeting = 'Good day';
    } else {
        greeting = 'Good evening';
    }

    console.log(greeting);
</script>
````

## 익명함수
+ 함수이름을 주지 않고 리터럴 방식으로 만들어진 이름없는 함수를 익명함수 라고 부른다.
+ 단 한번만 사용되는 함수의 경우(재사용 안함), 불필요한 시간동안 메모리를 차지하지 않도록 따로 함수의 이름을 갖지 않는다. 
+ 함수자체가 '식'이기 때문에 함수를 변수에 할당할 수 있다. 또한 다른 함수의 매개변수로 사용할 수 있다.
+ 변수 할당했으니 함수 이름처럼 사용해서 익명 함수를 실행한다. 
+ 함수가 이름을 갖는 것과 변수에 저장되는 것은 다르다.
+ 함수에서 return은 함수의 실행을 강제종료한다. 그러므로 reture문 아래의 로직은 작동하지 않는다.

````
<script>
    // 익명함수는 연결된 이름이 없는 함수
    // 익명함수 선언 및 변수에 대입
    let sayHello = function () {
        document.write("안녕하세요 <br>")
    }

    sayHello(); // 변수 sayHello에 할당했으니 함수 이름처럼 사용해서 익명 함수를 실행한다.
</script>
````

> 익명함수 + return
````
<script>
    function func() {
        document.write("1. 함수가 실행되었습니다. <br>");
        return; 

        document.write("2. 함수가 실행되었습니다."); // 실행안됨
    }

    func();
</script>
````

> 익명함수 선언 후 변수에 할당
````
<script>
    /*
    function(x, y) {
        return x + y;
    }
    */

    // 위의 익명 함수는 이름이 없어서 이름으로 호출을 할 수 없다.

    // 호출을 하려면 변수에 저장한 후에 변수의 이름을 통해 호출해야 한다.
    const add = function(x, y) {
        return x + y;
    }
    add(1, 2); // 3
</script>
````

## 함수 표현식(Function Expressions)
+ 변수를 선언하고 함수를 대입하는 방식을 함수 표현식이라고 한다.
+ 함수를 생성하고 변수에 값을 할당하는 것처럼 함수를 변수에 할당한다.

````
 <script>
    const 변수명 = function(매개변수 목록) {
        코드 실행부
    }

    변수명(인수 목록)
</script>
````

> 두 수를 더해서 반환하는 익명 함수
````
<script>
    // 매개변수 + 리턴문
    let add = function (a, b) {
        return a + b;
    }

    // 익명 함수 실행 후 결과값을 변수 sum에 저장.
    let sum = add(100, 200)
    document.write(sum)
</script>
````


