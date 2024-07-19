# 03-변수의 스코프

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

> 스코프의 구분
> + 전역 스코프(Global scope)
> + 지역 스코프(Local scope) 

## 전역 스코프(Global scope) 
+ 바깥 스코프 라고하며 어디에서든 참조 할수있다.
+ 전역 변수(Global variable) : 바깥쪽 전역에서 선언된 변수 어디든 참조 가능하다.

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
+ 지역 스코프에는 함수 스코프와 블록 스코프가 있다.
+ { 중괄호 }를 기준으로 범위가 구분된다.
+ 안쪽 스코프 라고하며 블록 안, 함수 내에서만 참조 할수있다.
+ 지역 변수(Local variable) : 안쪽 지역내에 선언된 변수 안에서만 참조 가능하다.

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
> 함수 스코프와 블록 스코프(function scope & block scope)
> + 함수 스코프(function scope) :  function{ } 안에있는 범위를 함수 스코프
> + 블록 스코프(block scope) :  function 을 제외한 if나 for 등의 { 중괄호 } 안에 있는 범위를 블록 스코프


### 함수 스코프
+ 함수가 선언되면 하나의 스코프(접근 범위)가 발생하는데 이걸 함수스코프라고 한다. 
+ 함수 스코프는 함수에서 선언한 변수는 해당 함수 내에서만 접근 가능하다는 걸 의미한다.
+ 아래 예시처럼 함수 외부에서 aa를 호출하면 undefined 에러가 뜬다.

> 함수 스크프와 var
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

### 블록 스코프
+ 블록 스코프는 블록 { 중괄호 } 내부에서 선언된 변수는 해당 블록에서만 접근 가능한 걸 말한다.
+ let, const로 선언된 변수가 블록 스코프 방식을 따른다.

> 블록 스코프와 let
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

> 블록 스코프와 const
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

### var, let, const 스코프 비교
|  | var | let | const |
| --- | :---: | :---: | :---: |
| 범위 | 함수 스코프(function scope) | 블록 스코프(block scope) | 블록 스코프(block scope) |
| 변수 중복선언 |  O  | X | X |
| 변수 값 재할당 |  O | O | X |
| 초기화 필요 | X | X | O |


   


