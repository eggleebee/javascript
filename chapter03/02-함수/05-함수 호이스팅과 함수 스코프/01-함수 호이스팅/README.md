# 02-함수
# 02-05-함수 호이스팅과 함수 스코프
# 02-05-01-함수 호이스팅

## 함수 호이스팅(function hoisting)이란?
+ 함수 선언문이 코드의 최상단으로 끌어 올려진 것처럼 동작하는 자바스크립트의 고유 특징을 함수 호이스팅(function hoisting)이라고 한다.

## 함수 생성 시점과 함수 호이스팅
+ 함수 선언문은  런타임(runtime) 이전에 자바스크립트 엔진에 의해 먼저 실행되어 함수 객체가 먼저 생성이 된다. 
+ 코드가 실행될 시 이미 생성된 함수의 객체를 참조할 수 있으며 심지어 호출까지 가능하다. 
+ 함수 선언식은 코드가 실행되기 전에 로드되지만, 함수 표현식은 인터프리터가 해당 코드 줄에 도달 할 때만 로드된다.
+ 함수 선언식은 var 문과 유사하게 호이스팅 된다. 
+ 반면, 함수 표현식은 호이스팅되지 않으므로 정의 된 범위에서 로컬 변수의 복사본을 유지할 수 있다.
+ 함수 표현식은 함수 이름이 필요없기에 가독성이 더 높은 장점이 있다.
+ 함수 호이스팅은 함수를 호출하기 이전에 반드시 함수를 정의해야한다는 당연한 규칙을 무시한다. 이같은 문제 때문에 함수 선언문 대신 함수 표현식을 사용할것이 권장된다.

> 함수 선언에서의 호이스팅 비교
````
<script>
    foo1(); // 함수 선언문에서는 호이스팅 일어난다.
    foo2(); // 함수 표현식이라서 호이스팅 안된다.

    function foo1() {
        console.log('Hello');
    }
    var foo2 = function() {
        console.log('world');
    }
</sctipt>
````

> 함수 선언식의 호이스팅
````
<script>
    // 함수 선언문으로 정의한 함수는 함수 선언 전에 호출할 수 있음
    console.log(add) 

    // 함수 선언식
    function add(x, y) {
        return x + y;
    }

    // greet 함수는 선언 전에 호출되었음에도 불구하고 정상적으로 작동한다.
    // 이는 함수 선언식이 호이스팅되기 때문.
    console.log(greet()); // "Hello, World!"

    function greet() {
        return "Hello, World!";
    }
</script>
````

> var로 선언된 함수 표현식의 호이스팅
````
<script>
    // 함수 표현식은 호이스팅되지 않음
    // 에러 발생! foo 함수는 아직 로드안됨
    // TypeError: foo is not a function
    console.log(foo());

    var foo = function () {
        return 5;
    }
</script>
````

> var로 선언된 함수표현식(매개변수) 이전에 함수를 참조
````
<script>
    // TypeError: plus is not a function
    // 함수 표현식으로 정의한 함수는 반드시 함수 표현식 이후에 참조 또는 호출해야 한다.
    console.log(plus())

    // 함수 표현식
    var plus = function (x, y) {
        return x + y;
    }
</script>
````

> var로 선언된 함수 표현식의 변수 호이스팅
````
<script>
    var result; // var로 선언된 (함수 표현식) 변수는 호이스팅되어 undefined로 초기화
    console.log(result)

    // 변수는 undefined이고
    // undefined는 함수가 아니기 때문에 
    // 이 함수를 선언하기 전에 호출하려고 하면 TypeError가 발생
    result = minus(100, 50);
    console.log(result)

    // 함수를 함수표현식으로 변수에 할당하면 변수 호이스팅 규칙을 따른다.
    let minus = function (a, b) {
        return a - b;
    }
</script>
````