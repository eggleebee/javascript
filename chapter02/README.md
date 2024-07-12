# 01-연산자
## 산술 연산자
+ 산술연산자는 숫자들의 산술적인 연산을 수행합니다 (상수, 변수 모두 연산가능)
+ 일반적인 산술연산자는 두개의 수를 연산합니다.

| 연산자 | 의미 | 설명 | 예제 |
|------|---|---|---|
| + | 덧셈 | 숫자들을 더하는 덧셈 연산자입니다. |var x = 5; <br> var y = 2; <br> var z = x + y; |
| - | 뺄셈 | 숫자들을 빼는 뺄셈 연산자입니다. | var x = 5; <br> var y = 2; <br> var z = x - y; |
| * | 곱셈 | 숫자들을 곱하는 곱셈 연산자입니다. | var x = 5; <br> var y = 2; <br> var z = x * y; |
| / | 나누기 | 숫자들을 나누는 나누기 연산자입니다. | var x = 5; <br> var y = 2; <br> var z = x / y; |
| % | 나머지 | 몫을 제외한 나머지값을 반환하는 나머지 연산자입니다. | var x = 5; <br> var y = 2; <br> var z = x % y; |
| ++ | 가산(증가) | 숫자를 증가시키는 가산연산자입니다. | var x = 5; <br> x++; <br> var z = x; |
| -- | 감산(감소) | 숫자를 감소시키는 가산연산자입니다. | var x = 5; <br> x--; <br> var z = x; |
| ** | 제곱 | 첫번째 피연산자를 두번째 피연산자의 갯수만큼 곱합니다. | var x = 5; <br> var z = x**2; // 결과값은 25 |

````
<script>
    var x = 20;
    var y = 3;
    var result;

    result = x + y; // 더하기
    document.write(result, "<br>");

    result = x - y; // 빼기
    document.write(result, "<br>");

    result = x * y; // 곱하기
    document.write(result, "<br>");

    result = x / y; // 나누기
    document.write(result, "<br>");

    result = x % y; // 나머지
    document.write(result);
</script>
````

````
<script>
    var num = 1;
    console.log("num++ 한 경우");
    console.log(num); // 처음에 변수에 저장된 1을 의미
    console.log(num++); // 처음에 변수에 저장된 1에 1을 더해라 라는 의미
    console.log(num); // 덧셈 결과를 확인
</script>
````

## 문자 결합 연산자
+ 문자 결합 연산자는 연산 대상 데이터가 문자형이다. 
+ 여러개의 문자를 하나의 문자형 데이터로 결합할 때 사용한다.

````
<script>
    var text1 = "큰 따옴표에 들어간 문자열입니다";
    var text2 = '작은 따옴표에 들어간 문자열 입니다.';
    var text3 = "순자가 '안녕하세요?' 라고 했습니다.";
    var text4 = '철수가 "안녕하세요?" 라고 말했습니다.';
    var text5 = "영자가 \"안녕하세요?\" 라고 말했습니다.";
    var text6 = `광수가 "안녕하세요" 라고 말했습니다.`;
    console.log(text1, text2, text3, text4, text5, text6);

    var result = text3 + text4 + text5 + text6;
    document.write(result);

    var age = 25;
    var userName = "홍길동";

    document.write("<hr>");
    document.write("제 이름은 " + userName + "이고" + "<br>" + "나이는 " + age + "세 입니다.");

    document.write("<hr>");
    document.write("제 이름은 " , userName , "이고" , "<br>" , "나이는 " , age , "세 입니다");

    document.write("<hr>");
    document.write(`제이름은 ${userName}`)
</script>
````

## 대입 연산자
+ 대입 연산자(=)는 연산된 데이터를 최종적으로 변수에 저장할 사용한다.
````
<script>
    var num1 = 10;
    var num2 = 3;
</script>
````

## 복합 대입 연산자
+ 복합 대입 연산자(+=, -=, *=, /=, %=)는 
+ 산술 연산자와 대입 연산자가 복합적으로 적용된 것을 말한다.

````
<script>
    var num1 = 10;
    var num2 = 3;

    num1 += num2;  //num1 = num1 + num2;
    document.write(num1, "<br>");

    num1 -= num2;  //num1 = num1 - num2;
    document.write(num1, "<br>");

    num1 *= num2; //num1 = num1 * num2;
    document.write(num1, "<br>");

    num1 %= num2; //num1 = num1 % num2;
    document.write(num1, "<br>");

    // HTML 태그들을 복합 대입 연산자를 이용하여 하나의 문자로 결합하려면 아래처럼 할 수 있다.
    var t = "<table border='1'>";

    t += "<tr>";
    t += "<td>첫번째 칸</td><td>두번째 칸</td><td>세번째 칸</td>";
    t += "<tr>";
    t += "</table>";

    document.write(t);
</script>
````

## 증감 연산자
+ 증감 연산자에는 숫자형 데이터를 1씩 증가시키는 증가 연산자(++)가 있고, 
+ 1씩 감소시키는 감소 연산자(–)가 있다.
+ 증감 연산자는 앞에서 배운 연산자와는 다르게, 피연산자가 한개만 필요한 단항 연산자이다.
+ 증감 연산자는 변수의 어느 위치에 오는지에 따라 결과값이 달라진다.

````
<script>
    var x = ++x; // 변수 x의 데이터를 1 증가시킨 뒤에 변수 x에 저장함
    var y = y++; // 변수 y에 변수 y의 데이터를 저장하고난 뒤에 변수 y의 데이터를 1 증가시킴

    var num1 = 10;
    var num2 = 20;
    var result;

    num1--;
    document.write(num1, "<br>"); //10에서 1 감소된 값인 9가 출력됨

    num1++;
    document.write(num1, "<br>"); // 9에서 1 증가된 값인 10이 출력됨

    result = num2++;
    document.write(result, "<br>"); // 대입 연산자가 먼저 실행되고, 증가 연산자가 실행되기 때문에 20이 출력됨

    result = ++num2;
    document.write(result, "<br>"); // 증가 연산자가 먼저 실행되고, 대입 연산자가 실행되기 때문에 22가 출력됨
</script>
````

## 비교 연산자
+ 두 데이터를 크다, 작다, 같다와 같이 비교할 때 사용하는 연산자이다. 
+ 연산된 결과의 값은 참 또는 거짓으로 논리형 데이터를 반환한다.

| 연산자 | 의미 |
|------|---|
| A > B | A가 B보다 크다 |
| A < B | A가 B보다 작다 |
| A >= B | A가 B보다 크거나 같다 |
| A <= B | A가 B보다 작거나 같다 |
| A == B | A와 B는 같다 |
| A != B | A와 B는 다르다 |
| A === B  | A와 B는 같다(데이터 타입 비교) |
| A !== B  | A와 B는 다르다(데이터 타입 비교) |

````
<script>
    var a = 10, b = 20, c = 10, d = "20", result;

    result = a == 10 // true
    result = b === 20 // true

    result = a > b; // false
    result = a < b; // true
    result = a <= b; //true

    result = b == d; // 데이터 타입과 상관없이 데이터 값이 같으므로 true
    result = b === d; // 데이터 타입이 다르므로 false (b는 number, d는 string) 

    result = a != b; // 데이터 값이 다르므로 true
</script>
````

## 논리 연산자
+ 논리 연산자에는 ||(or), &&(and), !(not)이 있다. 
+ 논리 연산자는 피연산자가 논리형 데이터인 true와 false로 결과를 반환한다.

> + || - OR 연산자는 연산자 왼쪽과 오른쪽의 값이 모두 false이면 false, 한 쪽이라도 true이면 true 를 반환한다.
> + && - AND 연산자는 연산자 왼쪽과 오른쪽의 값이 모두 true이면 true, 한 쪽이라도 false이면 false 를 반환한다.
> + ! - NOT 연산자는 truthy 한 값이 들어오면 false를 반환하고, falsy 한 값이 들어오면 true 를 반환한다.

````
<script>
    // 논리합(||) 연산자 OR 또는
    // 두개 이상의 조건이 있을때
    // 조건 중 하나라도 만족하면 결과는 true이다
    true || true   // true
    true || false  // true
    false || true  // true
    false || false // false

    // 논리곱(&&) 연산자 AND 그리고 
    // 두개 이상의 조건이 있을때
    // 두개 이상의 조건을 모두 만족(true)했을 때 결과는 true이다
    true && true   // true
    true && false  // false
    false && true  // false
    false && false // false

    // 논리 부정(!) 연산자
    !true  // false
    !false // true

    var height = 160;
    var age = 15;

    // 키가 180이상 그리고 나이가 20세 이상 그리고 나이가 30세 이하인가?
    height >= 180 && age >= 20 && age <= 30; // false

    // 나이가 18세 보다 작거나 65세 보다 큰가?
    age < 18 || age > 65;
</script>
````

### Truthy & Falsy
+ 자바스크립트에는 truthy와 falsy 라는 개념이 있다. 
+ 참/거짓을 판단하는 컨텍스트에서 truthy 한 값은 true로, falsy 한 값은 false로 판단된다.

> falsy 로 판단되는 값은 다음과 같다. (falsy한 값을 제외한 모든 값은 truthy 이다.)
> + 0
> + -0
> + 0n
> + ""
> + null
> + undefined
> + NaN

## 연산자 우선순위
+ 학교 수학시간에 배웠듯이 사칙연산에서는 곱하기가 우선적으로 연산됩니다.
+ 곱하기와 나누기 연산이 덧셈과 뺄셈 연산보다 우선적으로 실행됩니다.
+ 만약 기존 우선순위를 무시하고 먼저 연산을 하고 싶은 부분이 있다면, 해당 연산자와 피연산자를 ( 소괄호 )로 감싸면 됩니다.
+ 괄호를 묶은 연산자가 제일 먼저 연산이 되지만, 만약 아래와 같이 모두 우선순위가 같은 연산자가 나열되어 있다면 보통 왼쪽에서 오른쪽으로 순차적으로 연산이 됩니다.

> [자바스크립트 연산자 우선순위 수치 참고] <https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Operator_precedence>


| 순위 | 기능 | 연산자 | 연산자 | 연산자 | 연산자 | 연산자 | 연산자 |
|------|---|---|---|---|---|---|---|
| 1 | 괄호 | ( ) | | | | | |
| 2 | 증감 연산자, not | ++ | -- | ! | | | |
| 3 | 산술 연산자 곱셈, 나누기, 나머지 | * | / | % | | | |
| 4 | 산술 연산자 덧셈, 뺄셈 | + | - |  | | | |
| 5 | 비교 연산자 대소 | < | <= | > | >= | | |
| 6 | 비교 연산자 같음, 같지않음(다름) | == | === | != | !== | | |
| 7 | 논리 연산자 and | && | | | | | |
| 8 | 논리 연산자 or | || | | | | | |
| 9 | 대입 연산자 | = | += | -= | *= | /= | %= | | |

````
    1  +  2  **  3  *  4  /  5
    │    │└─ 1. ─┘       │   │
    │    └────── 2. ─────┘   │
    └───────────── 3. ───────┘

````

````
   (1 + ( (2 ** 3) * 4 / 5) ) 
   │    │ └─ 1. ─┘        │ │
   │    └────── 2. ───────┘ │
   └────────── 3. ──────────┘
````

````
   (1 + ( ( (2 ** 3) * 4 ) / 5) )
   │    │ │ └─ 1. ─┘     │    │ │
   │    └─│─────── 2. ───│────┘ │
   └──────│───── 3. ─────│──────┘
          └───── 4. ─────┘
````

````
<script>
    var result1 = 100 + 50 - 3; // 147
    var result2 = 100 + 50 * 3; // 곱하기 먼저 계산 후 덧셈 250
    var result3 = (100 + 50) * 3; // 괄호 먼저 계산 450
</script>
````

# 02-제어문
+ 제어문은 조건에 따라 코드 블록을 실행하거나 반복 실행할 때 사용한다. 
+ 일반적으로 코드는 위에서 아래방향으로 순차적으로 실행되는데, 제어문을 사용하면 코드의 실행 흐름을 인위적으로 제어할 수 있다.

## 블록문
+ 블록문은 문을 { 중괄호 }로 묶은 것으로, 코드 블록 또는 블록이라고 부르기도 한다.
+ 자바스크립트는 블록문을 하나의 실행 단위로 취급합니다. 
+ 블록문은 단독으로 사용할 수도 있으나 일반적으로 제어문이나 함수를 정의할 때 사용합니다.
+ 문의 끝에는 세미콜론을 붙이는 것이 일반적이지만, 블록문은 언제나 문의 종료를 의미하는 자체 종결성을 갖기 때문에 블록문의 끝에는 세미콜론을 붙이지 않는다.

````
<script>
    // 블록문
    {
        let foo = 10;
    }

    // 제어문 
    let x = 1;
    if (x < 10) {
        x++;
    }

    //함수 선언문
    function sum(a, b) {
        return a + b;
    }
</script>
````

## 조건문
+ 조건문은 주어진 조건식의 평과 결과에 따라 블록문의 실행을 결정한다. 
+ 조건식은 불리언으로 평가될 수 있는 표현식이며, 자바스크립트는 if...else문과 switch문, 두 가지 조건문을 제공한다.

````
<script>
    if (조건식 1) {
        // 조건식 1이 참이면 이 코드 블록이 실행
    } else if (조건식 2) {
        //조건식 2가 참이면 이 코드 블록이 실행
    } else {
        //조건식 1과 조건식 2가 모두 거짓이면 이 코드 블록이 실행
    }
</script>
````

## if, else if 문
+ if...else문은 주어진 조건식(불리언 값으로 평가될 수 있는 표현식)의 평가 결과(참 또는 거짓)에 따라 실행할 코드 블록을 결정한다. 
+ 조건식의 평가 결과가 true일 경우 if문의 코드 블록이 실행되고, 
+ false일 경우 else문의 코드블록이 실행된다. 
+ 조건식을 추가하여 조건에 따라 실행될 코드 블록을 늘리고 싶으면 else if문을 사용한다.
+ else if문과 else문은 사용할 수도 있고 사용하지 않을 수도 있다.
+ if문과 else문은 2번 이상 사용할 수 없지만 else if문은 여러 번 사용할 수 있다.
+ 만약 코드 블록 내의 문이 하나라면 중괄호를 생략할 수 있다.

````
<script>
    // if
    if (!false) {
        console.log('안녕')
    }

    if (true) {
        console.log('반가워')
    }

    if (true) {
        console.log('잘가')

    }
</script>
````

````
<script>
    // if, else
    let x = 2;

    if (10 % x === 0) {
        console.log('실행1')
    }

    if (33 % x === 0) {
        console.log('실행2')
    } else {
        console.log('33을 2로 나눈 나머지가 0이 아닐 경우에 실행됩니다.')
    }
</script>
````

````
<script>
    var age = 12;
    var charge;

    if (age < 8) {
        charge = 1000;
        document.write("미 취학 아동입니다.");
    }
    if (age < 14) {
        charge = 2000;
        document.write("초등학생 입니다.");
    }
    if (age < 20) {
        charge = 2500;
        document.write("중, 고등학생 입니다.");
    }
    else {
        charge = 3000;
        document.write("일반인 입니다.");
    }
</script>
````

````
<script>
    // 한 묶음으로 하고 싶다면
    // 하나의 상황에 대한 조건이 여러개로 나뉘고 각 조건에 다른 수행이 이루어져야 할 경우 사용
    // if- else if 를 사용하는 경우 하나의 조건이 만족 되면 나머지 else if 부분은 수행되지 않음
    if (false) {
        console.log('안녕하세요')
    } else if (true) {
        console.log('홍길동입니다')
    } else if (true) {
        console.log('반갑습니다')
    } else {
        console.log('잘가~~~')
    }
</script>
````

````
<script>
    const score = 96;

    if (score >= 90) {
        console.log("당신의 등급은 A")
    } else if (score >= 80) {
        console.log("당신의 등급은 B")
    } else if (score >= 70) {
        console.log("당신의 등급은 C")
    } else if (score >= 60) {
        console.log("당신의 등급은 D")
    } else {
        console.log("당신의 등급은 F")
    }
</script>
````

````
<script>
    let drink = prompt("가격 조회를 원하는 음료수를 입력하세요.( 콜라, 사이다, 커피 中 택1)", "");

    if (drink = "콜라") {
        document.write("800원");
    } else if (drink = "사이다") {
        document.write("900원");
    } else if (drink = "커피") {
        document.write("700원");
    } else {
        document.write("잘못된 단어 입력");
    }
</script>
````

````
<script>
    // 코드 블록 내의 문이 하나라면 중괄호를 생략
    var num = 2;
    var kind;

    if (num > 0) kind = '양수';
    else if (num < 0) kind = '음수';
    else kind = '0';
</script>    
````

## if 이중중첩문을 활용한 조건문
+ if 문 안에 if 문이 들어있는 것을 이중중첩문이라고 한다.
+ 이중중첩문은 바깥쪽에 있는 조건식1을 통과해야지만 안에 들어있는 조건식2을 실행한다.
+ 바깥쪽에 있는 조건식1을 통과하지 못할 시에는 안에 들어있는 조건식2는 실행되지 않는다.
+ 이때 조건식 1의 {}에 해당되는 실행내용(코드)만 실행된다.

````
<script>
    //기본형
    if (조건식1) {
        if (조건식2) {   
            실행내용 (코드작성)
        }
    }
</script>
````

````
 <script>
    var userId = "apple";
    var password = 12345;

    if (userId === "apple") {    // 만약 아이디가 apple이면 아래 if문을 실행, 아니면 실행하지 X
        if (password === 12345) { // 바깥 조건식이 통과하면, 실행된다. 
            console.log('로그인 되었습니다')   // 비번이 12345를 입력한다면 조건식을 통과하면 '로그인 되었습니다'출력
        } else {                 // 만약 아이디가 apple인데, 비번을 틀리게 입력했다면? 
            console.log('비밀번호가 일치하지 않습니다.')
        }    // 안에 if문은 실행되지 않고, "비밀번호가 일치하지 않습니다" 문구가 출력된다.
    } 
</script>
````

````
 <script>
    let useID = "silver";
    let usePW = "1234";

    let id = prompt("아이디가 무엇인가요?");
    let pw = prompt("비밀번호가 무엇인가요?");

    if (useID == id) {
        //아이디가 같을 때
        if (usePW == pw) {
            document.write(id + "님 반갑습니다.");
        } else {
            document.write("비밀번호가 틀렸습니다.");
        }
    } else {
        //아이디가 다를 때
        document.write("아이디가 일치하지 않습니다.");
    }
</script>
````

## switch문
+ if...else문은 논리적 참, 거짓으로 실행할 코드 블록을 결정한다. 반면에 switch문은 다양한 상황(case)에 따라 실행할 코드 블록을 결정할 때 사용한다.
+ switch문은 주어진 표현식을 평가하여 그 값과 일치하는 표현식을 갖는 case문으로 실행 흐름을 옮긴다.
+ case문은 상황을 의미하는 표현식을 지정하고 콜론으로 마친다. 
+ 그리고 그 뒤에 실행할 문들을 위치시킨다.
+ switch문의 표현식과 일치하는 case문이 없다면 실행 순서는 default문으로 이동한다. 
+ default문은 선택사항으로, 사용할 수도 있고 사용하지 않을 수도 있다.
+ case문에 해당하는 문의 마지막에 break문을 사용하지 않는다면 문을 실행한 후 switch문을 탈출하지 않고 switch문이 끝날 때까지 이후의 모든 case문과 default문을 실행하게 된다. 이를 폴 스루라고 말한다.
+ default문에는 break문을 생략하는 것이 일반적이다. default문은 switch문의 맨 마지막에 위치하므로 default문의 실행이 종료되면 switch문을 빠져나가기 때문이다.

### break문의 역할과 이유
> break는 switch의 중괄호를 빠져나가는 명령어다.
> witch조건문은 break문을 만나기 전까지 조건값들을 비교하여 case문 혹은 default문을 실행한다. 

### switch문 장점 : 간결성, 가독성
> switch 조건문은 if else if 조건식으로 변환할 수 있다.
> 두 식을 비교해보면 switch 조건문이 조금더 간결하고 가독성이 높다.

````
<script>
    switch (표현식) {
        case 표현식1:
            switch문의 표현식과 표현식1이 일치하면 실행될 문;
            break;
        case 표현식2:
            switch문의 표현식과 표현식2가 일치하면 실행될 문;
            break;
        default:
            switch문의 표현식과 일치하는 case문이 없을 때 실행될 문;
    }
</script>
````

````
 <script>
        const engDay = 'friday';
        let korDay;

        switch (engDay) {
            case 'monday':
                korDay = '월요일';
                break;
            case 'tuesday':
                korDay = '화요일';
                break;
            case 'wednesday':
                korDay = '수요일';
                break;
            case 'thursday':
                korDay = '목요일';
                break;
            case 'friday':
                korDay = '금요일';
                break;
            default:
                korDay = '주말';
                break;
        }

        console.log(korDay)
    </script>
````

````
 <script>
    const site = '구글';
    let url;

    switch( site ) {
        case '네이버' :
            url = 'https://www.naver.com';
            break;
        case '구글' :
            url = "https://www.google.co.kr"
            break;
        case '다음' :
            url = "https://www.daum.net"
            break;
        default :
            document.write('사이트를 확인하세요!')
            break;
    }

    console.log( url )
</script>
````

> prompt 함수의 경우, 입력 받은 값이 숫자인지 문자인지 상관없이 string 타입으로 입력된다. 따라서 입력받은 값이 숫자일 경우, number로 형 변환을 한 후에 연산을 하는 등의 추가적인 코드 작성에 있어 parseInt 함수는 유용하게 사용된다.

## parseInt 란?
> 자바스크립트에 내장되어 있는 함수로, 말 그대로 문자열을 파싱하여 문자열에 포함된 숫자를 찾아서 number로 형변환을 시켜준다.

````
<script>
    let age = prompt('당신의 나이는 몇살입니까? 예시) 17, 18, 19')

    switch( parseInt(age) ){
        case 17 : 
            alert('고등학교 1학년 입니다');
            break;
        case 18 :
            alert('고등학교 2학년 입니다');
            break;
        case 19 :
            alert('고등학교 3학년 입니다');
            break;
        default :
            alert('나이를 잘못 입력하셨습니다');
            break;
    }

    console.log( '입력받은 나이는?', age )
    console.log( '입력받은 나이의 데이터 타입 확인', typeof age ) // string
    console.log( age + 100 ) // + 문자끼리 연결연산자

    console.log( age - 10 ) // 자동형변환되어 숫자로 계산이 된 것임
    console.log( age * 20 ) // 자동형변환되어 숫자로 계산이 된 것임

    let x = "156";
    console.log('x값의 타입은?' , typeof x ) // string

    x = Number(x)
    
    console.log( 'x값의 타입은?', typeof x ) // number
    console.log( 'x값?', x ) // 

    let y = "789"
    console.log('y값의 타입은?' , typeof y ) // string

    y = parseInt( y )
    console.log('y값의 타입은?' , typeof y ) // number
</script>
````

