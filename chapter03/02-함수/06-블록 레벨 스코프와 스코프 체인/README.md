# 02-함수
# 02-06-블록 레벨 스코프와 스코프 체인

## 블록 레벨 스코프(Block Level Scope)란?
+ let과 const를 사용하여 선언된 변수는 블록 레벨 스코프를 가진다. 
+ 해당 변수가 선언된 블록(중괄호 {} 안)에서만 접근 가능.


> 블록 스코프 내부 변수 출력
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

> 외부 함수 변수 출력

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


