# 02-함수
# 02-05-함수 호이스팅과 함수 스코프
# 02-05-01-함수 스코프

## 스코프(Scope)란?
+ 자바스크립트에서 스코프(Scope)란? 변수와 함수가 접근 가능한 범위를 의미한다. 
+ 이는 코드의 특정 영역에서 어떤 변수들을 사용할 수 있는지를 정의한다.

## 스코프의 구분
+ 글로벌 스코프(Global Scope) 
+ 함수 스코프(Function Scope) 
+ 블록 레벨 스코프(Block Level Scope) 

## 글로벌 스코프(Global Scope)
+ 글로벌 스코프에 선언된 변수는 어디서든 접근 가능. (전역 변수)

> 글로벌 스코프 전역 변수
````
<script>
    let globalVar = "전역 변수";

    function checkScope() {
        console.log(globalVar); // "전역 변수" 출력
    }

    checkScope();
    console.log(globalVar); // "전역 변수" 출력
</script>
````

## 함수 스코프(Function Scope) 
+ 함수 내에서 선언된 변수는 해당 함수 내에서만 접근 가능. 
+ 외부에서는 접근할 수 없다.


> 함수 스코프 내부 변수 출력
````
<script>
    // 함수 스코프(Function Scope) 
    function exampleFunction() {
        let functionScopedVar = "함수 스코프 내 변수";
        console.log(functionScopedVar); // "함수 스코프 내 변수" 출력
    }

    exampleFunction();
    console.log(functionScopedVar); // ReferenceError(참조 불가) 발생
</script>
````

> 매개변수와 같이 함수 안에서 정의된 변수
````
<script>
    function add(x, y) { // 매개변수 `x`와 `y`가 정의됨
        return x + y;
    }

    add(2, 3);

    // 이렇게, 매개변수와 같이 함수 안에서 정의된 변수는 함수 바깥에서는 접근할 수 없기 때문에 함수 안에서만 사용할 수 있다. 
    // 스코프(scope) : 변수는 코드의 일정 범위 안에서만 유효
    console.log(x); // 에러! ReferenceError: x is not defined
</script>
````

## 블록 레벨 스코프(Block Level Scope) 
+ let과 const를 사용하여 선언된 변수는 블록 레벨 스코프를 가진다. 
+ 해당 변수가 선언된 블록(중괄호 {} 안)에서만 접근 가능.

````
<script>
    // 블록 레벨 스코프(Block Level Scope)
    function testBlockScope() {
    if (true) {
        let blockScopedVar = "블록 스코프 내 변수";
        console.log(blockScopedVar); // "블록 스코프 내 변수" 출력
    }

    console.log(blockScopedVar); // ReferenceError(참조 불가) 발생
    }

    testBlockScope();
</script>
````

## 스코프 체인(Scope Chain)
+ 자바스크립트에서 함수는 중첩될 수 있다.
+ 내부 함수는 외부 함수의 변수에 접근할 수 있다.

````
<script>
    function outerFunction() {
    var outerVar = "외부 함수 변수";

    function innerFunction() {
        console.log(outerVar); // "외부 함수 변수" 출력
    }

    innerFunction();
    }

    outerFunction();
</script>
````


