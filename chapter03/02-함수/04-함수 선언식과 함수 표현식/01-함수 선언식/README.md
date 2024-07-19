# 02-함수
# 02-04-함수 선언식과 함수 표현식
# 02-04-01 함수 선언식

## 함수 선언식(Function Declarations)
+ function 키워드를 작성하면 함수를 정의할 수 있다. 함수 선언식은 'function' 키워드로 시작하고 함수 이름을 명시한다.
+ function 키워드를 작성하고, 함수 이름과 (매개변수 목록)을 작성한 후 { 코드블럭 }을 작성한다. 
+ 함수 선언문은 표현식이 아닌 문이다. 표현식이 아닌 문은 변수에 할당할 수 없으므로 함수 선언문도 변수에 할당불가능하다.

````
<script>
    function 함수이름(매개변수 목록) {
        함수 실행부 // 함수가 호출되면 실행되는 몸통부 코드블럭을 작성해준다.
    }
</script>
````

> (기명)함수 선언식
````
<script>
    // 함수 선언
    function 더하기() { console.log('더하기 함수 실행') }
    function 빼기() { console.log('빼기 함수 실행') }

    // 함수호출
    더하기();
    빼기();
</script>
````

> 힘수 선언식-매개변수 1개 + 리턴문
````
<script>
    // 함수 선언
    function add(x) {
        let sum = x + 100;
        return sum;
    }

    // 함수호출
    console.log(sum)
</script>
````

> 힘수 선언식-매개변수 2개 + 리턴문
````
<script>
    // 함수 선언
    function add(x, y) {
        const result = x + y;
        console.log(result);
        return result;
    }

    // 함수호출
    console.log(add)
</script>
````

