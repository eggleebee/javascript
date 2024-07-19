# 02-변수와 자료형
# 02-02-데이터 타입

## 자바스크립트의 데이터 타입
1. 원시 타입 (Primitive Type)
2. 참조타입(Object/Reference Type)

## 원시 타입 (Primitive Type)
> + Number
> + String
> + Boolean
> + Undefined
> + Null
> + Symbol(ES6에 추가, 객체 속성을 만드는 데이터 타입)
> + 원시 타입이 할당될 때는 변수에 값(value) 자체가 담긴다.(메모리 참조가 아닌 값의 복사)
> + 메모리상에 고정된 크기로 저장되며 원시 데이터 값 자체를 보관하므로 불변적이다.

### Number
모든 숫자를 실수로 처리

````
<script>
    console.log(typeof 1); // number

    let num_1 = 99;
    let num_2 = -99;
    console.log(typeof num_1); //Number
    console.log(typeof num_2); //Number
</script>
````
### String
+ UTF-16으로 구성된 문자열
+ 작은따옴표(''), 큰따옴표(""), 템플릿 리터럴(``)로 문자열을 할당
+ 템플릿 리터럴은 줄바꿈, 공백 모두 적용됨

### 이스케이프 시퀀스
> + 이스케이프 시퀀스는 프로그래밍 언어 특성상 표현할 수 없는 기능, 문자를 표현해준다. 
> + 백슬래시(\) 뒤에 한 문자나 숫자 조합이 오는 문자 조합을 “이스케이프 시퀀스”라고 한다.
> + 줄 바꿈 문자, 작은따옴표, 또는 문자 상수의 다른 특정 문자를 나타내려면 이스케이프 시퀀스를 사용해야 한다. 
> + \t 탭(수평)  \n 줄바꿈 문자  \’ 작은따옴표  \” 큰따옴표

````
<script>
    console.log(typeof "abc"); // string

    let str_1 = 'Hi';
    let str_2 = "안녕";
    let str_3 = `안녕\n하세요  \n\t반갑습니다`;

    console.log(str_1);
    console.log(str_2);
    console.log(str_3);

    const msg = "행복\n하세요";
    console.log(msg)
    console.log(typeof msg)

    let score = "68"
    let sum = score + 20
    console.log(score)
    console.log(typeof score) //string
    console.log(sum)
</script>
````

### Boolean(불리언)
true, false
````
<script>
    console.log(typeof true); // boolean
    console.log(typeof false); // boolean

    let bool_1 = true;
    let bool_2 = 2 > 3;
    console.log(typeof bool_1); //boolean
    console.log(typeof bool_2); //boolean
</script>
````

### Undefined 
+ 자바스크립트에서 undefined는 의도치 않게 누락된 값을 나타내기 위해서 주로 사용된다. 
+ 보통 개발자가 값을 설정하지 않았을 때 프로그래밍 언어 차원에서 자연스럽게 알아서 설정되는 경우가 많습니다.
+ 값도 타입도 undefined

````
<script>
    // 변수를 선언할 때 초기화를 하지 않으면 undefined가 할당
    let x;
    console.log(x); // undefined
    console.log(typeof x); // 'undefined'

    // 함수를 호출할 때도 매개 변수를 넘기지 않으면 undefined가 할당
    function foo(x, y) {
        return { x, y };
    }

    foo(1); // { x: 1, y: undefined }
</script>
````

### Null
+ 의도적으로 '값이 없음'을 명시하기 위해 할당하는 값
+ Null의 값 체크를 위해서는 일치연산자(===)를 사용
+ typeof 연산결과는 초기 자바스크립트의 버그로 수정하면 파장이 클까봐 그냥 두고있다 함.

````
<script>
    let nu = null;
    console.log(typeof nu);	//object
    console.log(nu === null); //true
</script>
````

## 참조타입(Object/Reference Type)
> + 객체(Object)
> + 배열(Array)
> + 함수(Fuction)
> + 원시타입이 아닌 모든 것
> + 참조타입은 원시타입 데이터의 집합이다.
> + 참조 타입은 고정된 크기의 보관함이 아니다.
> + 참조 타입을 변수에 할당할 때는 값이 아닌 데이터의 주소를 저장한다.

### 객체(Object) : {}

````
<script>
    console.log(typeof { a: 1, b: 2 }); // object

    let obj = {};
    console.log(typeof obj); // object
</script>
````

### 배열(Array) : []
+ 배열은 'object'의 특수한 한 형태이기 때문에 typeof만으로는 객체가 배열인지 확인할 수 없음
+ 객체가 배열인지 확인하기 위해서는 'isArray()' 함수를 사용해야 함

````
<script>
    let arr = [1,2,3,4];
    console.log(typeof arr); //object

    console.log(Array.isArray(arr)); //true
    console.log(Array.isArray({}));  //false
</script>
````

### 함수(Fuction) : function(){}

````
 <script>
    let func = function(){};
    console.log(typeof func); //function
    
    function add(x, y) {
        return x + y;
    }
    console.log(typeof add); // function
</script>
````



       





   


