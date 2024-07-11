# 01-자바스크립트 시작

## 자바스크립트(JavaScript)란?
+ HTML은 **웹의 내용을 작성, 구조화**
+ CSS는 **웹페이지를 꾸미고 디자인**
+ JavaScript는  **웹의 동작을 구현**

## ECMAScript 자바스트립트 버전
1. ES1 (초판, 1997)
2. ES2 (1998)
3. ES3 (1999)
4. ES5 (2009, 엄격모드, 배열메서드(map, filter, forEach 등), JSON 등)
5. ES6 (2015, ECMAScript 2015)
6. ES7 (2016, ECMAScript 2016, 이하 생략)
7. ES6 부터 const, let, Promise, Arrow function, class 등의 문법들이 대거 추가
8. ECMA-인터내셔널 공식 사이트 : <https://www.ecma-international.org>

## 자바스크립트 삽입위치
+ head, body의 문서 처음, 중간, 끝
+ 보통 body의 맨 끝

## 내부 스크립트와 외부 스크립트
+ 비교적 간단한 코드로 구성되며 현재 파일에만 적용되는 경우 내부 자바스크립트를 사용.
+ 공통기능 구현이나 소스가 길어지면 외부 자바스크립트로 관리함.
+ 공통 라이브러리로 개발된 경우 CDN을 통해 외부 서버로 부터 참조해서 사용함.

### 내부 JavaScript

스크립트는 <script> (script 태그) 를 이용해 HTML 문서의 대부분의 위치에 삽입할 수 있습니다.

````
<!DOCTYPE html>
<html>
    <head></head>
    <body>
        <h1>JavaScript</h1>
        <script>
            console.log('hello')
        </script>
    </body>
</html>
````

### 외부 JavaScript

자바스크립트 코드의 양이 많은 경우, 자바스크립트 코드를 script 태그 안에 전부 작성하기 보다는 여러개의 자바스크립트 파일로 기능별로 나누어 작성해서 관리하는 것이 편리합니다.

````
<!DOCTYPE html>
<html>
    <head></head>
    <body>
        <h1>JavaScript</h1>
        <script src="js/script.js"></script>
    </body>
</html>
````

## 브라우저 동작 방식

1. HTML을 읽기 시작합니다.
2. HTML을 파싱합니다.
3. DOM 트리를 생성합니다.
4. CSS 파싱 후 스타일 규칙 생성
5. DOM 트리와 생성된 스타일 규칙 Attachment
6. Render 트리 형성 후 Layout, Painting
7. Display

> 파싱이란, 프로그램을 실행할 수 있도록 내부 포맷에 맞게 분석하고 변환하는 것을 의미한다.

## JavaScript 소스파일 위치 결정
브라우저는 HTML의 구조와 CSS 스타일을 렌더링하는 도중 자바스크립트를 만나게 되면 이에 대한 해석과 구현이 완료될때까지 브라우저 렌더링을 멈추게 됩니다. 즉, 자바스크립트의 삽입 위치에 따라 스크립트 실행순서와 브라우저 렌더링에 영향을 미치기 때문에 다음 사항을 고려해 적절한 
위치선정이 필요 합니다.

```` 
<head></head>
````

+ 브라우저 렌더링에 방해가 될 수 있으며 무거운 스크립트가 실행되는 경우 오랫동안 화면이 보여지지 않을수 있음.
+ 문서를 초기화하거나 설정하는 가벼운 스크립트들을 주로 사용.
+ 문서의 DOM(Document Object Model) 구조가 필요한 경우 HTML이 모두 로드 된 이후 실행되어야 하므로 window.onload와 같은 로드 이벤트가 추가되어야 함.

```` 
<body></body>
````

+ 태그내 모든 위치에 둘 수 있음.
+ 웹페이지 로딩이 완료된 다음 실행하기 위해 일반적으로는 </body> 바로 앞에 위치.
+ 이경우 문서의 DOM 구조가 완료된 시점에 실행되기에 별다른 추가설정이 필요없음.

## JavaScript 코드구조
+ 문(statement)은 세미콜론으로 구분(세미콜론을 붙이지 않는 곳도 있습니다.)
+ 문은 값, 연산자, 키워드, 명령어, 표현식(값으로 평가, 함수나 key, index를 통한 값의 호출도 표현식) 등으로 구성됩니다.

## JavaScript 주석

````
<script>
    // 한 줄 주석입니다.
    /*
    여
    러
    줄
    주석입니다.
    */
</script>
````    

## JavaScript를 출력하는 4가지 방법
1. 문서 내에 요소를 선택하여 출력하는 방법(innerHTML, innerText)
2. 문서 내에 직접 출력하는 방법(document.write)
3. 사용자 인터렉션(alert, confirm)
4. 콘솔에 찍는 방법(console.log)

````
<!DOCTYPE html>
<html>
<head></head>

<body>
    <h1>JavaScript</h1>
    <div id="box"></div>
    <script>
        document.getElementById('box').innerHTML = '박스입니다.';
        document.write("<h1>제목입니다.</h1>");
        //alert('경고창에 출력');
        //confirm('확인창에 출력');
        console.log('콘솔창에 출력');
    </script>
</body>
</html>
````
# 02-변수

## 변수란?
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
| snake_case | 모든 단어 사이를 언더바_로 표기하는 기법 | hellow_world, HELLO_WORLD | 상수 |


## 변수선언 3가지 방법
1. var
2. let
3. const

자바스크립트의 변수는 다음과 같이 선언합니다.

````
var 변수명;
var 변수명 = 값;

let 변수명;
let 변수명 = 값;

const 변수명;
const 변수명 = 값;
````

## 변수의 타입
> + 자바스크립트에는 타입(Type)이라는 개념이 있다.
> + 타입이란 변수에 할당할 수 있는 데이터 형태를 말한다. ex)숫자, 문자
> + 즉, 변수에는 숫자나 문자 등 다양한 형태의 데이터 타입을 담을 수 있다.
> + 데이터 타입에 따라 할 수 있는 일이 다르다.
> + 즉, 타입마다 다른 속성과 메서드가 있다.
> + typeof : 변수의 타입을 반환하는 자바스크립트 키워드
> + undefined : '아직 할당하지 않은 값'을 표현하기 위해 사용하는 값

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

## Number
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
## String
+ UTF-16으로 구성된 문자열
+ 작은따옴표(''), 큰따옴표(""), 템플릿 리터럴(``)로 문자열을 할당
+ 템플릿 리터럴은 줄바꿈, 공백 모두 적용됨

## 이스케이프 시퀀스
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

## Boolean(불리언)
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

## Undefined 
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

## Null
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

## 객체(Object) : {}

````
<script>
    console.log(typeof { a: 1, b: 2 }); // object

    let obj = {};
    console.log(typeof obj); // object
</script>
````

## 배열(Array) : []
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

## 함수(Fuction) : function(){}

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

## 스코프의 구분
> + 전역 스코프(Global scope)
> + 지역 스코프(Local scope) 

## 전역 스코프(Global scope) 
바깥 스코프 라고하며 어디에서든 참조 할수있다.
> 전역 변수(Global variable) : 바깥쪽 전역에서 선언된 변수 어디든 참조 가능하다.

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
안쪽 스코프 라고하며 블록 안, 함수 내에서만 참조 할수있다.
> 지역 변수(Local variable) : 안쪽 지역내에 선언된 변수 안에서만 참조 가능하다.

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

## 함수 스코프와 블록 스코프(function scope & block scope)
> + 지역 스코프에는 함수 스코프와 블록 스코프가 있다.
> + { 중괄호 }를 기준으로 범위가 구분된다.
> + var은 블록스코프를 무시한다.

| 함수 스코프(function scope) | 블록 스코프(block scope) | 
| --- | --- |
| function{ } 안에있는 범위를 함수 스코프 | function 을 제외한 if나 for 등의 { 중괄호 } 안에 있는 범위를 블록 스코프 |

## 함수 스코프와 var
+ 함수가 선언되면 하나의 스코프(접근 범위)가 발생하는데 이걸 함수스코프라고 한다. 
+ 함수 스코프는 함수에서 선언한 변수는 해당 함수 내에서만 접근 가능하다는 걸 의미한다.
+ 아래 예시처럼 함수 외부에서 aa를 호출하면 undefined 에러가 뜬다.
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

## 블록 스코프와 let, const
> + 블록 스코프는 블록 { 중괄호 } 내부에서 선언된 변수는 해당 블록에서만 접근 가능한 걸 말한다.
> + let, const로 선언된 변수가 블록 스코프 방식을 따른다.

## 블록 스코프와 let
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

## 블록 스코프와 const
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

## hoisting(호이스팅)
> + 호이스팅은 코드가 실행하기 전 **변수선언/함수선언이 해당 스코프의 최상단으로 끌어 올려진 것 같은 현상**을 말한다.
> + 자바스크립트 엔진은 코드를 실행하기 전 실행 가능한 코드를 형상화하고 구분하는 과정(*실행 컨텍스트를 위한 과정)을 거친다.
> + 자바스크립트 엔진은 코드를 실행하기 전 실행 컨텍스트를 위한과정에서 모든 선언(var, let, const, function, class)을 스코프에 등록한다.
> + 코드 실행 전 이미 변수선언/함수선언이 저장되어 있기 때문에 선언문보다 참조/호출이 먼저 나와도 오류 없이 동작한다. (정확히는 var 키워드로 선언한 변수와 함수 선언문일 경우 오류 없이 동작한다. 이는 선언이 파일의 맨 위로 끌어올려진 것 처럼 보이게 한다.)
> + **실행 컨텍스트**는 실행 가능한 **코드가 실행되기 위해 필요한 환경을 의미**하고 실행되기전 이러한 실행 컨텍스트 과정(코드를 구분하는 과정)을 거친다.

## 변수는 어떻게 생성되며, 호이스팅은 어떻게 이뤄질까?
변수는 3단계에 걸쳐 생성된다.

1. 1단계: 선언 단계(Declaration phase)
+ 변수를 실행 컨텍스트의 변수 객체에 등록한다.
+ 이 변수 객체는 스코프가 참조하는 대상이 된다.

2. 2단계: 초기화 단계(Initialization phase)
+ 변수 객체에 등록된 변수를 위한 공간을 메모리에 확보한다.
+ 이 단계에서 변수는 undefined로 초기화 된다.

3. 3단계: 할당 단계(Assignment phase)
+ undefined로 초기화된 변수에 실제 값을 할당한다.

## var로 선언한 변수 호이스팅
> var 키워드로 선언한 변수는 선언 단계와 초기화 단계가 한번에 이뤄진다. 즉, 스코프에 변수를 등록(선언 단계)하고 메모리에 변수를 위한 공간을 확보한 후, undefined로 초기화한다. 따라서 변수 선언문 이전에 변수에 접근하여도 스코프에 변수가 존재하기 때문에 에러가 발생하지 않는다. 다만 undefined를 반환한다. 이후 변수 할당문에 도달하면 비로소 값이 할당된다.

## let,const로 선언한 변수 호이스팅
> let 키워드로 선언된 변수는 선언 단계와 초기화 단계가 분리되어 진행된다. 즉, 스코프에 변수를 등록(선언 단계)하지만 초기화 단계는 변수 선언문에 도달했을 때(코드 실행 후) 이뤄진다. 초기화 이전에 변수에 접근하려고 하면 참조 에러가 발생한다. 이는 아직 변수가 초기화되지 않았기 때문이다. 즉, 변수를 위한 메모리 공간이 아직 확보되지 않았기 때문이다. 따라서 스코프의 시작 지점부터 초기화 시작 지점까지는 변수를 참조할 수 없다. 스코프의 시작 지점부터 초기화 시작 지점까지의 구간을 ‘일시적 사각지대(Temporal Dead Zone; TDZ)’라고 부른다.

## TDZ(Temporal Dead Zone)의 정의
> + TDZ 는 스코프의 시작 지점부터 초기화 시작 지점까지의 사각지대 구간을 뜻한다.(변수가 선언되고 초기화되기 사이의 사각지대)
> + let과 const는 var와는 다르게 선언단계와 초기화 단계가 따로 분리되어 실행된다.
> + 그래서 선언 단계와 초기화 단계 사이에서는 실행 컨텍스트에는 변수를 등록했지만 메모리가 할당되지 않은 상태라 ReferenceError 가 나오는 것이다.
> + var는 변수의 선언단계와 초기화단계가 동시에 실행되어 TDZ가 존재하지 않기 때문에 호이스팅이 일어나는 것이다.

````
<script>
    console.log(num); //Uncaught ReferenceError: Cannot access 'num' before initialization
    let num; //num을 초기화 하지 않을 경우 접근 안됨(일시적 사각지대로 들어감)
</script>
````




       





   


