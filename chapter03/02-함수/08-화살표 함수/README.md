# 02-함수
# 02-08-화살표 함수

## 화살표 함수란?
+ 함수 정의를 위한 새로운 표기법인 화살표 함수(arrow function)은 ES2015에서 도입되었다.
+ ES6 버전부터는 => 표기법(화살표 표기법)을 사용해 함수 선언을 더 간단하게 작성 할 수 있다. 
+ 화살표 함수는 함수를 변수에 할당하여 사용하는 함수 표현식의 한 유형이다. 
+ 화살표 함수는 함수 표현식으로 정의해야만 한다. (함수 선언문 불가)
+ 식별자에 화살표 함수를 할당하는 방식이며 function 표현에 비해 구문이 짧아 개발시에 편리하다.

> 일반 함수 선언식
````
<script>
    function add(a, b) {
        return a + b;
    };

    console.log( add(1, 2) ); // 3
</script>
````

> 일반 함수 표현식
````
<script>
    const add = function(a, b) {
        return console.log(a + b);
    };

    add(1, 2); // 3
</script>
````

> 화살표 함수 정의
````
<script>
    const sum = (a, b) => {
        return a + b;
    };

    console.log( sum(1, 2) ); // 3
</script>
````

> 중괄호 안에 함수 내용이 한 줄뿐인 단순한 리턴문(함수 몸체가 한줄의 구문)이라면 한줄로 더 심플하게 줄일 수 있다. 중괄호 생략가능! return 키워드도 생략가능! 암묵적으로 return된다. 

````
<script>
    // const add = (a, b) => { return a + b; };
    const add = (a, b) => a + b; 

    console.log( add(4, 5) ); // 9
</script>
````

````
<script>
    // const multiply = (x, y) => { return x * y };
    const multiply = (x, y) => x * y;

    console.log( multiply(2, 4) ); // 8
</script>
````

> 함수 내부가 단일 표현식(single expression)이 아닌 경우 즉, 함수 본문이 여러 줄인 화살표 함수는 {중괄호}와 return 키워드를 생략할 수 없다.
````
<script>
    let sum = (a, b) => {  // 중괄호는 본문 여러 줄로 구성되어 있음을 알려준다.
        let result = a + b;
        return result; // 중괄호를 사용했다면, return문으로 결과값을 반환해주어야 한다.
    };

    console.log( sum(1, 2) ); // 3
</script>
````
````
<script>
    const add = (a, b) => {
        const sum = a + b;
        console.log("Sum:", sum);

        return sum; // return 키워드를 생략할 수 없다.
    };

    const result = add(3, 5);
    console.log( "Result:", result ); // Sum: 8, Result: 8
</script>
````

> 매개변수가 하나밖에 없다면, 매개변수 부분의 (소괄호)를 쓰지 않아도 된다.
````
<script>
    var 두배만들기 = x => { return x * 2 }

    console.log( 두배만들기(4) ); // 8
    console.log( 두배만들기(8) ); // 16
</script>
````

````
<script>
    // let double = function(n) { return n * 2 }
    let double = n => n * 2;

    console.log( double(3) ); // 6
</script>
````

````
<script>
    let hi = user => document.write(user + "님, 안녕하세요?");

    hi("홍길동");
</script>
````

> 매개변수가 하나도 없을 땐 괄호를 비워놓으면 된다. 다만, 이 때 (소괄호)는 생략할 수 없다.

````
<script>
    // const hi = () => { return "안녕하세요?" };
    const hi = () => "안녕하세요?";

    document.write( hi() );
</script>
````

````
<script>
    let sayHi = () => alert("안녕하세요!");

    sayHi();
</script>
````

> 매개변수가 2개일 때 함수 내용이 한줄일 경우 중괄호와 return문 생략가능!
````
<script>
    // let add = (a,b) => {return a + b}
    let add = (a,b) => a + b;

    console.log( add(10, 20) );
</script>
````

> 화살표 함수는 표기법이 간단하기 때문에 익명 함수를 다른 함수의 인수로 넘길 때 주로 사용된다.
````
<script>
    [1, 2, 3, 4, 5].filter(x => x % 2 === 0);
</script>
````

## 화살표 함수를 쓰는 이유
+ 기존의 함수와 비교할 때 화살표 함수는 짧은 구문으로 함수를 더 간결하게 표현할 수 있다.
+ 대부분의 개발자들은 짧고 간결한 코딩을 원한다.

