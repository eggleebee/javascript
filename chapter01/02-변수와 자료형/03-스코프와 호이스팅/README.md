# 02-변수와 자료형
# 02-03-스코프와 호이스팅

## 스코프란?
+ 스코프(scope)는 변수에 접근할 수 있는 범위를 말한다.
+ 스코프는 크게 전역 스코프와 지역 스코프로 나눌 수 있다.
+ 스코프는 중첩이 가능하다.
+ 가장 바깥은 전역스코프라 하고 나머지는 지역스코프다.
+ 전역 스코프(global)는 어디에서든 해당 변수에 접근 가능한 걸 의미한다. (전역변수)
+ 바깥쪽 스코프에서 선언한 변수(전역변수)는 안쪽에서 사용가능하다
+ 지역 스코프(local)의 경우, 한정적인 범위에서 해당 변수에 접근이 가능하다. (지역변수)
+ 안쪽 스코프에서 선언한 변수(지역변수)는 바깥쪽에서 사용불가다.
+ 지역 변수가 전역변수보다 우선순위가 더 높다.

## 스코프의 구분
> + 전역 스코프(Global scope)
> + 지역 스코프(Local scope) 

## 전역 스코프(Global scope) 
바깥 스코프 라고하며 어디에서든 참조 할수있다.
> 전역 변수(Global variable) : 바깥쪽 전역에서 선언된 변수 어디든 참조 가능하다.

````
<script>
    // 전역(바깥쪽) 스코프
    let e, f, g;
    let userName;
    let age;

    {
        e = 10, f = 20, g = 30;
        console.log('변수값 출력', e, f, g)
    }

    if (true) {
        userName = "홍길동"
        age = 20
        console.log(userName)
        console.log(age)
    }

    console.log('변수값 출력', e, f, g)
    console.log(userName)
    console.log(age)
</script>
````   

## 지역 스코프(Local scope) 
안쪽 스코프 라고하며 블록 안, 함수 내에서만 참조 할수있다.
> 지역 변수(Local variable) : 안쪽 지역내에 선언된 변수 안에서만 참조 가능하다.

````
 <script>
    if(true){
        // 지역(안쪽) 스코프
        const menuName = "라면"
        const price = "4,000원"
        console.log(menuName, price) 
    }
    console.log(menuName, price)// 바깥쪽에서 참조불가
</script>
````

### 함수 스코프와 블록 스코프(function scope & block scope)
> + 지역 스코프에는 함수 스코프와 블록 스코프가 있다.
> + { 중괄호 }를 기준으로 범위가 구분된다.
> + var은 블록스코프를 무시한다.

| 함수 스코프(function scope) | 블록 스코프(block scope) | 
| --- | --- |
| function{ } 안에있는 범위를 함수 스코프 | function 을 제외한 if나 for 등의 { 중괄호 } 안에 있는 범위를 블록 스코프 |

### 함수 스코프와 var
+ 함수가 선언되면 하나의 스코프(접근 범위)가 발생하는데 이걸 함수스코프라고 한다. 
+ 함수 스코프는 함수에서 선언한 변수는 해당 함수 내에서만 접근 가능하다는 걸 의미한다.
+ 아래 예시처럼 함수 외부에서 aa를 호출하면 undefined 에러가 뜬다.
````
<script>
    function setNumber() {
        var num = '12'; // 함수 내부에서 선언
    }
    console.log(num); 
    // Uncaught ReferenceError: num is not defined
</script>
````

+ 만약 변수가 함수 내부에 선언된 것이 아니면 이 변수의 스코프는 전역 스코프(global)이므로
+ 어디에서든 접근이 가능하다.
````
<script>
    var setNumber = '123'; 
    console.log(setNumber)
</script>
````

+ var은 함수 내에서만 지역 변수로 유지되기 때문에, 
+ 아래 코드에서는 전역 변수로 취급된다.
+ var로 선언하면 블록에 의한 범위 제한이 없음
````
<script>
    {
        a = 10, b = 20, c = 30;
        console.log('변수값 출력', a, b, c)
    }

    if (true) {
        var num = '456';
        console.log(num) 
    }
    console.log(num)

    for (var index = 0; index < 5; index++) {
        console.log(index)
    }
    console.log(index)
</script>
````

### 블록 스코프와 let, const
> + 블록 스코프는 블록 { 중괄호 } 내부에서 선언된 변수는 해당 블록에서만 접근 가능한 걸 말한다.
> + let, const로 선언된 변수가 블록 스코프 방식을 따른다.

### 블록 스코프와 let
````
<script>
    function printMsg() {
        if (true) {
            let msg = "안녕";
            console.log("if문 안에서 접근", msg);
        }
        // console.log("if문 밖에서 접근 불가", msg);
        // Uncaught ReferenceError: msg is not defined
    }
    printMsg();
</sctipt>
````

````
<script>
   function printTxt() {
        let txt = "안녕";
        if (true) {
            let txt = "반가워"; // 이것은 if문 블록 내부에서만 유효하므로
            console.log(txt);
        }
        console.log(txt); // 같은 스코프안에 있는 안녕이 출력됨
    }
    printTxt();
</sctipt>
````

````
<script>
   function printCount() {
        let i;
        for (i = 0; i <= 2; i++) {
            console.log("printCount for문 안에서 접근", i)
        }
        console.log("printCount for문 밖에서 접근", i); // 0,1,2
    }
    printCount() // for문을 다 돌고난 후 i값은 3
</sctipt>
````

### 블록 스코프와 const
````
<script>
    // const로 선언한 변수는 재할당이 안됩니다.
    // Uncaught TypeError: Assignment to constant variable.
    const menuName = "떡볶이";
    const price = "3,000원";
    console.log(menuName, price) 

    if(true){
        menuName = "라면"
        price = "6,000원"
    }
    console.log(menuName, price)
</script>
````

## hoisting(호이스팅)
+ 호이스팅은 코드가 실행하기 전 **변수선언/함수선언이 해당 스코프의 최상단으로 끌어 올려진 것 같은 현상**을 말한다.
+ 자바스크립트 엔진은 코드를 실행하기 전 실행 가능한 코드를 형상화하고 구분하는 과정(*실행 컨텍스트를 위한 과정)을 거친다.
+ 자바스크립트 엔진은 코드를 실행하기 전 실행 컨텍스트를 위한과정에서 모든 선언(var, let, const, function, class)을 스코프에 등록한다.
+ 코드 실행 전 이미 변수선언/함수선언이 저장되어 있기 때문에 선언문보다 참조/호출이 먼저 나와도 오류 없이 동작한다. (정확히는 var 키워드로 선언한 변수와 함수 선언문일 경우 오류 없이 동작한다. 이는 선언이 파일의 맨 위로 끌어올려진 것 처럼 보이게 한다.)
+ **실행 컨텍스트**는 실행 가능한 **코드가 실행되기 위해 필요한 환경을 의미**하고 실행되기전 이러한 실행 컨텍스트 과정(코드를 구분하는 과정)을 거친다.

## 변수는 어떻게 생성되며, 호이스팅은 어떻게 이뤄질까?
+ 변수는 3단계에 걸쳐 생성된다.

> ### 1단계: 선언 단계(Declaration phase)
> + 변수를 실행 컨텍스트의 변수 객체에 등록한다.
> + 이 변수 객체는 스코프가 참조하는 대상이 된다.
> ### 2단계: 초기화 단계(Initialization phase)
> + 변수 객체에 등록된 변수를 위한 공간을 메모리에 확보한다.
> + 이 단계에서 변수는 undefined로 초기화 된다.
> ### 3단계: 할당 단계(Assignment phase)
> + undefined로 초기화된 변수에 실제 값을 할당한다.

## var로 선언한 변수 호이스팅
+ var 키워드로 선언한 변수는 선언 단계와 초기화 단계가 한번에 이뤄진다. 
+ 즉, 스코프에 변수를 등록(선언 단계)하고 메모리에 변수를 위한 공간을 확보한 후, undefined로 초기화한다. 
+ 따라서 변수 선언문 이전에 변수에 접근하여도 스코프에 변수가 존재하기 때문에 에러가 발생하지 않는다
+ 다만 undefined를 반환한다. 이후 변수 할당문에 도달하면 비로소 값이 할당된다.

````
<script>
    // 호이스팅 때문에 선언이 끌어올려져서 오류 안남.
    console.log(text); // (선언 + 초기화 된 상태)
    text = '안녕!'; // (선언 + 초기화 + 할당 된 상태)
    var text;
    console.log(text);
</script>
````

## let과 const로 선언한 변수 호이스팅
+ let 키워드로 선언된 변수는 선언 단계와 초기화 단계가 분리되어 진행된다. 
+ 즉, 스코프에 변수를 등록(선언 단계)하지만 초기화 단계는 변수 선언문에 도달했을 때(코드 실행 후) 이뤄진다. 
+ 초기화 이전에 변수에 접근하려고 하면 참조 에러가 발생한다. 이는 아직 변수가 초기화되지 않았기 때문이다. 
+ 즉, 변수를 위한 메모리 공간이 아직 확보되지 않았기 때문이다. 
+ 따라서 스코프의 시작 지점부터 초기화 시작 지점까지는 변수를 참조할 수 없다. 
+ 스코프의 시작 지점부터 초기화 시작 지점까지의 구간을 ‘일시적 사각지대(Temporal Dead Zone; TDZ)’라고 부른다.

````
<script>
    // 호이스팅 때문에 선언이 끌어올려졌지만 초기화 안된 상태에서 참조해서 오류 남.
    console.log(str); 
    // (선언 된 상태, 초기화(메모리 공간 확보와 undefined로 초기화) 안되서 참조 불가능 → 에러남 )
    // Uncaught ReferenceError: Cannot access 'str' before initialization
    let str; // 여기서 초기화 단계가 실행됨
</script>
````

## TDZ(Temporal Dead Zone)의 정의
+ var는 변수의 선언단계와 초기화단계가 동시에 실행되어 TDZ가 존재하지 않기 때문에 호이스팅이 일어난다.
+ TDZ 는 스코프의 시작 지점부터 초기화 시작 지점까지의 사각지대 구간을 뜻한다.(변수가 선언되고 초기화되기 사이의 사각지대)
+ let과 const는 var와는 다르게 선언단계와 초기화 단계가 따로 분리되어 실행된다.
+ 그래서 선언 단계와 초기화 단계 사이에서는 실행 컨텍스트에는 변수를 등록했지만 메모리가 할당되지 않은 상태라 ReferenceError 가 나오는 것이다.
+ 다시 말 해 let과 const는 호이스팅 되어 변수를 메모리에 올려놨지만 TDZ라는 지역에 있어 선언한 코드 줄을 지나야 접근 가능한 상태라고 보면 된다.

````
<script>
    console.log(num); // Uncaught ReferenceError: Cannot access 'num' before initialization
    let num; // num을 초기화 하지 않을 경우 접근 안됨(일시적 사각지대로 들어감)
</script>
````

       





   


