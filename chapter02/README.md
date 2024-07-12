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
> 복합 대입 연산자(+=, -=, *=, /=, %=)는 
> 산술 연산자와 대입 연산자가 복합적으로 적용된 것을 말한다.

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