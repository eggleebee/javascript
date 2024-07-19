# 02-변수와 자료형

## 변수(Variable)란?
자바스크립트에서 변수는 데이터를 담는 그릇을 의미한다.
스크립트 처리 과정에서 데이터를 일시적으로 담아두는 공간으로, 한 번에 하나의 값만 저장할 수 있습니다. 
그래서 한 변수에 데이터가 이미 존재하는데, 다른 값을 넣으려고 시도하는 경우에 기존의 값은 삭제되고 새로온 데이터가 저장됩니다.
변수는 var, let, const 키워드를 사용하여 선언하고,
할당 연산자(=)를 사용해 값을 할당한다.
그리고 식별자인 변수명을 사용해 변수에 저장된 값을 참조한다.(저장된 값을 보여준다)

## Javascript 변수 선언
1. 변수이름은 대소문자를 구별.
2. 여러 변수를 한번에 선언할 수 있음.
3. 지역변수와 전역변수가 있음.
4. 기본적으로 소문자로 시작되는 Camel Case를 사용.

## 변수 명명 규칙
+ 변수명의 첫 글자는 영문자, 달러스코어$, 언더바_만 올 수 있다.
+ 두 번째 이후 글자에는 영문자, 달러스코어, 언더바, 숫자만 올 수 있다.
+ 변수명의 영문자는 대.소문자를 엄격하게 구분한다.
+ 자바스크립트의 예약어가 아니어야 한다.

> 예약어(키워드) : 특별한 용도로 사용하기 위해 미리 예약해둔 단어들

자바스크립트의 예약어는 다음과 같습니다.

| 예약어 | 예약어 | 예약어 | 예약어 | 예약어 | 예약어 | 예약어 |
| ---- | --- | --- | --- | --- | --- | --- |
| abstract | arguments | await | boolean | break | byte |  |
| case | catch  | char | class | const  | continue |
| debugger | default | delete | do | double |  |  |
| else | enum | eval | export  | extends |  |  |
| false | final | finally | float | for | function  | goto |
| if | implements | import | in | instanceof | int | interface |
| let | long | native | new | null |  |  |
| package | private | protected | public | return |  |  |
| short | static | super | switch | synchronized |  |  |  
| this | throw | throws | transient | true | try | typeof | 
| void | var | volatile | while | with | yield | |


## 변수명 표기법
변수명 표기법은 대표적으로 세 가지 방식이 있습니다. 

| 표기법 | 설명 | 예시 | 사용처 | 
| ---- | --- | --- | --- |
| camelCase | 낙타의 등처럼 보인다고 해서 붙여진 이름. 이름의 맨 첫 번째, 단어의 첫 글자는 소문자로 적고, 두 번째 단어 부터는 첫 글자는 대문자로 적는 기법 | helloWorld | 변수, 함수 |
| PascalCase | 모든 단어의 첫 번째 글자를 대문자로 표기하는 기법 | HelloWorld | 클래스, 생성자 |
| snake_case | 모든 단어 사이를 언더바_로 표기하는 기법 | first_name, hellow_world, HELLO_WORLD, | 상수 |


## 변수선언 3가지 방법
1. var
2. let
3. const

자바스크립트의 변수는 다음과 같이 선언합니다.

````
<script>
    var 변수명;
    var 변수명 = 값;

    let 변수명;
    let 변수명 = 값;

    const 변수명;
    const 변수명 = 값;
</script>
````

## var (function scope)
+ var문에서 변수에 초기 값을 지정하지 않는다면, 변수는 값이 설정될 때까지 undefined 값을 갖게 된다.
+ var의 경우 변수를 한 번 더 선언해도 에러가 나지 않는다.

````
<script>
    var i; // 선언
    console.log(i); // undefined 가 저장됨

    var sum = 0;  // 선언과 초기화
    console.log(sum);

    var x, y, z; // 한 번에 여러 개의 변수를 함께 선언할 수 있음
    var x = 10; // x변수를 재선언후 값을 할당해도 에러가 나지 않음
    console.log(x);

    var i=0, sum=10, message="Hello";  // 선언과 초기화를 동시에 해줄 수 있음
    console.log(i, sum, message);
</script>
````

## let (block scope)
+ 이미 선언되었다는 에러 메세지가 나온다.
+ 변수 재선언은 안된다.
+ 하지만 변수 재할당은 가능하다.

````
 <script>
    let a; // 선언 후 할당을 나중에 해도 됨
    console.log(a) // undefined 가 저장됨

    let x, y, z;
    console.log(x, y, z);//undefined

    let year, month, day;
    let address = "서울시";
    console.log(month)//undefined

    let name;
    console.log(name)
    name = "홍길동";
    console.log(name);

    let fruit = "사과", price = 3000;
    console.log(fruit);
    console.log(price);
    console.log(fruit, price);
    console.log(fruit, "1개 가격은", price, "원 입니다.");

    // 중복선언불가 : Identifier 'b' has already been declared
    let user = "이순신";
    let user = "강감찬";
    console.log(user);
</script>
````

## const (block scope)
+ 변수 재선언, 재할당 모두 불가능하다.
+ 처음 선언할 때, 반드시 초기화를 해야한다.
+ 바뀌지 않을 값은 const로 선언해주면 된다.
+ 보통 대문자를 사용해서 선언한다. (강제는 아니지만 관습!)

````
<script>
    const num = 20; // 선언과 동시에 할당을 해야함
    const MY_NUM = 7; // 보통 대문자를 사용해서 선언 
    console.log(num, MY_NUM);

    const msg = "안녕하세요";
    console.log(msg);

    //const 선언만 하는 것은 불가, 반드시 초기화
    const txt ;
    txt = "안녕";
    console.log(txt); 
</script>
````

## 여러 변수를 선언
+ 하나의 키워드(var, let, const)를 사용하여 변수마다 콤마(,)줄바꿈하여 선언한다.

````
<script>
    // bad
    var first_Name = '길동';
    var age = 20;
    var hobby = ['수영','등산'];
    var married = false;
    var items = getItems();

    // good
    var first_Name = '홍길동',
        age = 20,
        hobby = ['수영','등산'],
        married = false;
        items = getItems();



    function getItems(){
        // 실행문
    }    
</script>
````

## 변수의 타입
> + 자바스크립트에는 타입(Type)이라는 개념이 있다.
> + 타입이란 변수에 할당할 수 있는 데이터 형태를 말한다. ex)숫자, 문자
> + 즉, 변수에는 숫자나 문자 등 다양한 형태의 데이터 타입을 담을 수 있다.
> + 데이터 타입에 따라 할 수 있는 일이 다르다.
> + 즉, 타입마다 다른 속성과 메서드가 있다.
> + typeof : 변수의 타입을 반환하는 자바스크립트 키워드
> + undefined : '아직 할당하지 않은 값'을 표현하기 위해 사용하는 값




       





   


