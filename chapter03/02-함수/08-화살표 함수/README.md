# 02-함수
# 02-08-화살표 함수

## 화살표 함수란?
+ 함수 정의를 위한 새로운 표기법인 화살표 함수(arrow function)은 ES2015에서 도입되었다.
+ ES6 버전부터는 => 표기법(화살표 표기법)을 사용해 함수 선언을 더 간단하게 작성 할 수 있다. 
+ 화살표 함수라고 하는데 익명 함수에서만 사용할 수 있다.
+ 식별자에 화살표 함수를 할당하는 방식이며 function 표현에 비해 구문이 짧아 개발시에 편리하다.

````
<script>
    const hi = funtion(){
        return "안녕하세요?";
    }
</script>
````

````
<script>
    const hi = () => { return "안녕하세요?" };
</script>
````

````
<script>
    // 중괄호 안에 함수 내용이 한 줄뿐이라면 중괄호 생략가능! return문도 생략가능! 
    const hi = () => "안녕하세요?";
</script>
````

````
<script>
    // 매개변수가 하나밖에 없다면, 매개변수 부분의 괄호를 쓰지 않아도 된다.
    let hi = user => document.write(user + "님, 안녕하세요?");
</script>
````

````
<script>
    // 매개변수가 2개일 때
    let hi = (a,b) => {return a + b}
</script>
````

````
<script>
    // 함수 내용이 한줄 이니까 중괄호와 return문 생략가능!
    let hi = (a,b) => a + b;
</script>
````

````
<script>
    // 화살표 함수는 표기법이 간단하기 때문에 익명 함수를 다른 함수의 인수로 넘길 때 주로 사용된다.
    [1, 2, 3, 4, 5].filter(x => x % 2 === 0);
</script>
````


