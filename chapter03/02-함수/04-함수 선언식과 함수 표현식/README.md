# 02-함수
# 02-04-함수 선언식과 함수 표현식

## 자바스크립트 함수 생성 2가지 방법
+ 함수 선언식(Function Declarations) 
+ 함수 표현식(Function Expressions)


## 호이스팅(function hoisting)
+ 호이스팅이란  선언한 변수 및 함수가 선언 범위의 최상단으로 올라가 작동하는 것을 의미한다.
+ 이는 변수나 함수가 실제 코드에서 작성된 위치와 관계없이 선언 단계에서 메모리에 저장되기 때문에 발생한다.
+ 호이스팅은 크게 변수 호이스팅, 함수 호이스팅으로 나누어져 있다.

> + var 호이스팅 방식 : 메모리에 변수 선언 + 'undefind'값으로 초기화 하여 접근가능
> + let/const 호이스팅 방식 : 메모리에 변수 선언 단 TDZ에 있어 접근 불가

### 변수 호이스팅(Hoisting)
````
<script>
    number=3
    console.log(number); // 3

    var number = 5;
    console.log(number); // 5

    console.log(num) // undefind
    var num = 3
</script>
````

### let, const'로 선언한 mylet, youLet은 왜 'ReferenceError'가 나올까?
+ 호이스팅은 정말 단순히 최상단으로 올려주는 역할 뿐이고
+ 그 이후에 var과 다르게 let, const는 다른 과정이 추가된다.
+ 다시 말 해 let과 const는 호이스팅 되어 변수를 메모리에 올려놨지만 TDZ라는 지역에 있어 선언한 코드 줄을 지나야 접근 가능한 상태라고 보면 된다.

````
<script>
    console.log(x); // ReferenceError
    let x = 10;

    console.log(y); // ReferenceError
    const y = 10;
</script>
````

## 함수 선언식과 함수 표현식의 차이점

|   |  정의  |  함수이름 | 호이스팅 | 함수 호출 |
|---|---|---|---|---|
| 함수 선언식 | 'function' 키워드로 시작하고 함수 이름을 명시 <br><br> function add(x,y) <br> { <br> return x+y; <br> } | 이름을 가질 수 있으며, 이 이름은 함수 내부에서만 접근 가능. | 함수 선언식은 호이스팅이 된다. 함수가 선언되기 전에도 호출할 수 있다. <br> 호이스팅되어 함수 전체가 스코프의 최상단으로 끌어올려진다. | 사용하려면 해당 함수 이름을 호출하면 된다. <br><br> add(1,2)|
| 함수 표현식 | 표현식을 사용하여 정의 될 수 있으며, 함수 표현식은 변수로 저장될수 있다. <br><br> var sum = function(x,y) <br> { <br> return x+y; <br> } | 함수 표현식으로 정의를 하게 될 때는 함수의 이름을 생략할 수 있는데 이러한 함수를 익명 함수라고 한다. <br> 함수 표현식을 사용할 때에는 함수의 이름을 생략하는 것이 일반적이다. | 변수 호이스팅 규칙을 따르므로 호이스팅되지 않으며 선언되기 전에는 호출할 수 없다. <br> 함수를 선언하기 전에 호출하려고 하면, TypeError 발생. | 함수 표현식이 변수에 저장되면, 변수는 함수처럼 사용 가능해진다. <br> 변수에 저장된 함수는 함수명이 필요 없으며, 변수 이름을 통하여 호출된다. <br><br> sum(100,200) |

