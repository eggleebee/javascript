# 02-제어문
+ 제어문은 조건에 따라 코드 블록을 실행하거나 반복 실행할 때 사용한다. 
+ 일반적으로 코드는 위에서 아래방향으로 순차적으로 실행되는데, 제어문을 사용하면 코드의 실행 흐름을 인위적으로 제어할 수 있다.

## 블록문
+ 블록문은 문을 { 중괄호 }로 묶은 것으로, 코드 블록 또는 블록이라고 부르기도 한다.
+ 자바스크립트는 블록문을 하나의 실행 단위로 취급합니다. 
+ 블록문은 단독으로 사용할 수도 있으나 일반적으로 제어문이나 함수를 정의할 때 사용합니다.
+ 문의 끝에는 세미콜론을 붙이는 것이 일반적이지만, 블록문은 언제나 문의 종료를 의미하는 자체 종결성을 갖기 때문에 블록문의 끝에는 세미콜론을 붙이지 않는다.

````
<script>
    // 블록문
    {
        let foo = 10;
    }

    // 제어문 
    let x = 1;
    if (x < 10) {
        x++;
    }

    //함수 선언문
    function sum(a, b) {
        return a + b;
    }
</script>
````

## 조건문
+ 조건문은 주어진 조건식의 평과 결과에 따라 블록문의 실행을 결정한다. 
+ 조건식은 불리언으로 평가될 수 있는 표현식이며, 자바스크립트는 if...else문과 switch문, 두 가지 조건문을 제공한다.

````
<script>
    if (조건식 1) {
        // 조건식 1이 참이면 이 코드 블록이 실행
    } else if (조건식 2) {
        //조건식 2가 참이면 이 코드 블록이 실행
    } else {
        //조건식 1과 조건식 2가 모두 거짓이면 이 코드 블록이 실행
    }
</script>
````

### if, else if 문
+ if...else문은 주어진 조건식(불리언 값으로 평가될 수 있는 표현식)의 평가 결과(참 또는 거짓)에 따라 실행할 코드 블록을 결정한다. 
+ 조건식의 평가 결과가 true일 경우 if문의 코드 블록이 실행되고, 
+ false일 경우 else문의 코드블록이 실행된다. 
+ 조건식을 추가하여 조건에 따라 실행될 코드 블록을 늘리고 싶으면 else if문을 사용한다.
+ else if문과 else문은 사용할 수도 있고 사용하지 않을 수도 있다.
+ if문과 else문은 2번 이상 사용할 수 없지만 else if문은 여러 번 사용할 수 있다.
+ 만약 코드 블록 내의 문이 하나라면 중괄호를 생략할 수 있다.

````
<script>
    // if
    if (!false) {
        console.log('안녕')
    }

    if (true) {
        console.log('반가워')
    }

    if (true) {
        console.log('잘가')

    }
</script>
````

````
<script>
    // if, else
    let x = 2;

    if (10 % x === 0) {
        console.log('실행1')
    }

    if (33 % x === 0) {
        console.log('실행2')
    } else {
        console.log('33을 2로 나눈 나머지가 0이 아닐 경우에 실행됩니다.')
    }
</script>
````

````
<script>
    var id = prompt("아이디를 입력하세요");
    var pw = prompt("비밀번호를 입력하세요");

    // 아이디가 핑크초코 이고 비밀번호가 1234일 때 
    // 문서에 "환영합니다" 라고 출력
    // false 일때는 
    // 문서에 "아이디, 비밀번호를 확인하세요" 라고 출력

    if (id == "핑크초코" && pw == "1234") {
        document.write("환영합니다");
    } else {
        document.write("아이디, 비밀번호를 확인하세요");
    }
</script>
````

````
<script>
    var age = 12;
    var charge;

    if (age < 8) {
        charge = 1000;
        document.write("미 취학 아동입니다.");
    }
    if (age < 14) {
        charge = 2000;
        document.write("초등학생 입니다.");
    }
    if (age < 20) {
        charge = 2500;
        document.write("중, 고등학생 입니다.");
    }
    else {
        charge = 3000;
        document.write("일반인 입니다.");
    }
</script>
````

````
<script>
    // 한 묶음으로 하고 싶다면
    // 하나의 상황에 대한 조건이 여러개로 나뉘고 각 조건에 다른 수행이 이루어져야 할 경우 사용
    // if- else if 를 사용하는 경우 하나의 조건이 만족 되면 나머지 else if 부분은 수행되지 않음
    if (false) {
        console.log('안녕하세요')
    } else if (true) {
        console.log('홍길동입니다')
    } else if (true) {
        console.log('반갑습니다')
    } else {
        console.log('잘가~~~')
    }
</script>
````

````
<script>
    const score = 96;

    if (score >= 90) {
        console.log("당신의 등급은 A")
    } else if (score >= 80) {
        console.log("당신의 등급은 B")
    } else if (score >= 70) {
        console.log("당신의 등급은 C")
    } else if (score >= 60) {
        console.log("당신의 등급은 D")
    } else {
        console.log("당신의 등급은 F")
    }
</script>
````

````
<script>
    let drink = prompt("가격 조회를 원하는 음료수를 입력하세요.( 콜라, 사이다, 커피 中 택1)", "");

    if (drink = "콜라") {
        document.write("800원");
    } else if (drink = "사이다") {
        document.write("900원");
    } else if (drink = "커피") {
        document.write("700원");
    } else {
        document.write("잘못된 단어 입력");
    }
</script>
````

````
<script>
    var food = prompt("먹고싶은 음식을 입력하세요.[떡볶이, 돈까스, 피자, 치킨 중에 입력]");

    // 떡볶이, 떡뽁이, 떡뽀끼 

    if (food == "떡볶이" || food == "떡뽁이" || food == "떡뽀끼") {
        document.write("오늘 점심은 떡볶이 입니다");
    } else if (food == "돈까스") {
        document.write("오늘 점심은 돈까~~스 입니다");
    } else if (food == "피자") {
        document.write("오늘 점심은 피자~~~입니다");
    } else if (food == "치킨") {
        document.write("오늘 점심은 치~~~킨~~~입니다");
    } else {
        document.write("메뉴를 다시 입력하세요.");
    }
</script>
````

````
<script>
    // 코드 블록 내의 문이 하나라면 중괄호를 생략
    var num = 2;
    var kind;

    if (num > 0) kind = '양수';
    else if (num < 0) kind = '음수';
    else kind = '0';
</script>    
````

### if 이중중첩문을 활용한 조건문
+ if 문 안에 if 문이 들어있는 것을 이중중첩문이라고 한다.
+ 이중중첩문은 바깥쪽에 있는 조건식1을 통과해야지만 안에 들어있는 조건식2을 실행한다.
+ 바깥쪽에 있는 조건식1을 통과하지 못할 시에는 안에 들어있는 조건식2는 실행되지 않는다.
+ 이때 조건식 1의 {}에 해당되는 실행내용(코드)만 실행된다.

````
<script>
    //기본형
    if (조건식1) {
        if (조건식2) {   
            실행내용 (코드작성)
        }
    }
</script>
````

````
 <script>
    var userId = "apple";
    var password = 12345;

    if (userId === "apple") {    // 만약 아이디가 apple이면 아래 if문을 실행, 아니면 실행하지 X
        if (password === 12345) { // 바깥 조건식이 통과하면, 실행된다. 
            console.log('로그인 되었습니다')   // 비번이 12345를 입력한다면 조건식을 통과하면 '로그인 되었습니다'출력
        } else {                 // 만약 아이디가 apple인데, 비번을 틀리게 입력했다면? 
            console.log('비밀번호가 일치하지 않습니다.')
        }    // 안에 if문은 실행되지 않고, "비밀번호가 일치하지 않습니다" 문구가 출력된다.
    } 
</script>
````

````
 <script>
    let useID = "silver";
    let usePW = "1234";

    let id = prompt("아이디가 무엇인가요?");
    let pw = prompt("비밀번호가 무엇인가요?");

    if (useID == id) {
        //아이디가 같을 때
        if (usePW == pw) {
            document.write(id + "님 반갑습니다.");
        } else {
            document.write("비밀번호가 틀렸습니다.");
        }
    } else {
        //아이디가 다를 때
        document.write("아이디가 일치하지 않습니다.");
    }
</script>
````

### switch문
+ if...else문은 논리적 참, 거짓으로 실행할 코드 블록을 결정한다. 반면에 switch문은 다양한 상황(case)에 따라 실행할 코드 블록을 결정할 때 사용한다.
+ switch문은 주어진 표현식을 평가하여 그 값과 일치하는 표현식을 갖는 case문으로 실행 흐름을 옮긴다.
+ case문은 상황을 의미하는 표현식을 지정하고 콜론으로 마친다. 
+ 그리고 그 뒤에 실행할 문들을 위치시킨다.
+ switch문의 표현식과 일치하는 case문이 없다면 실행 순서는 default문으로 이동한다. 
+ default문은 선택사항으로, 사용할 수도 있고 사용하지 않을 수도 있다.
+ case문에 해당하는 문의 마지막에 break문을 사용하지 않는다면 문을 실행한 후 switch문을 탈출하지 않고 switch문이 끝날 때까지 이후의 모든 case문과 default문을 실행하게 된다. 이를 폴 스루라고 말한다.
+ default문에는 break문을 생략하는 것이 일반적이다. default문은 switch문의 맨 마지막에 위치하므로 default문의 실행이 종료되면 switch문을 빠져나가기 때문이다.

### break문의 역할과 이유
> break는 switch의 중괄호를 빠져나가는 명령어다.
> witch조건문은 break문을 만나기 전까지 조건값들을 비교하여 case문 혹은 default문을 실행한다. 

### switch문 장점 : 간결성, 가독성
> switch 조건문은 if else if 조건식으로 변환할 수 있다.
> 두 식을 비교해보면 switch 조건문이 조금더 간결하고 가독성이 높다.

````
<script>
    switch (표현식) {
        case 표현식1:
            switch문의 표현식과 표현식1이 일치하면 실행될 문;
            break;
        case 표현식2:
            switch문의 표현식과 표현식2가 일치하면 실행될 문;
            break;
        default:
            switch문의 표현식과 일치하는 case문이 없을 때 실행될 문;
    }
</script>
````

````
 <script>
        const engDay = 'friday';
        let korDay;

        switch (engDay) {
            case 'monday':
                korDay = '월요일';
                break;
            case 'tuesday':
                korDay = '화요일';
                break;
            case 'wednesday':
                korDay = '수요일';
                break;
            case 'thursday':
                korDay = '목요일';
                break;
            case 'friday':
                korDay = '금요일';
                break;
            default:
                korDay = '주말';
                break;
        }

        console.log(korDay)
    </script>
````

````
 <script>
    const site = '구글';
    let url;

    switch( site ) {
        case '네이버' :
            url = 'https://www.naver.com';
            break;
        case '구글' :
            url = "https://www.google.co.kr"
            break;
        case '다음' :
            url = "https://www.daum.net"
            break;
        default :
            document.write('사이트를 확인하세요!')
            break;
    }

    console.log( url )
</script>
````

## prompt 함수의 경우
> 입력 받은 값이 숫자인지 문자인지 상관없이 string 타입으로 입력된다. 따라서 입력받은 값이 숫자일 경우, number로 형 변환을 한 후에 연산을 하는 등의 추가적인 코드 작성에 있어 parseInt 함수는 유용하게 사용된다.

## parseInt 란?
> 자바스크립트에 내장되어 있는 함수로, 말 그대로 문자열을 파싱하여 문자열에 포함된 숫자를 찾아서 number로 형변환을 시켜준다.

````
<script>
    let age = prompt('당신의 나이는 몇살입니까? 예시) 17, 18, 19')

    switch( parseInt(age) ){
        case 17 : 
            alert('고등학교 1학년 입니다');
            break;
        case 18 :
            alert('고등학교 2학년 입니다');
            break;
        case 19 :
            alert('고등학교 3학년 입니다');
            break;
        default :
            alert('나이를 잘못 입력하셨습니다');
            break;
    }

    console.log( '입력받은 나이는?', age )
    console.log( '입력받은 나이의 데이터 타입 확인', typeof age ) // string
    console.log( age + 100 ) // + 문자끼리 연결연산자

    console.log( age - 10 ) // 자동형변환되어 숫자로 계산이 된 것임
    console.log( age * 20 ) // 자동형변환되어 숫자로 계산이 된 것임

    let x = "156";
    console.log('x값의 타입은?' , typeof x ) // string

    x = Number(x)
    
    console.log( 'x값의 타입은?', typeof x ) // number
    console.log( 'x값?', x ) // 

    let y = "789"
    console.log('y값의 타입은?' , typeof y ) // string

    y = parseInt( y )
    console.log('y값의 타입은?' , typeof y ) // number
</script>
````

## 반복문
+ 반복문은 조건식의 평가 결과가 참인 경우 코드 블록을 실행한다. 
+ 그 후 조건식을 다시 평가하여 여전히 참인 경우에는 코드 블록을 다시 실행하고 조건식이 거짓일 때까지 반복한다.
+ 자바스크립트는 for문, while문, do...while문, 세 가지 반복문을 제공한다.

### for문
+ for문은 조건식이 거짓으로 평가될 때까지 코드 블록을 반복 실행합니다.
+ for문 내에서 for문을 중첩해 사용할 수 있습니다. 이를 중첩 for문 이라고 합니다.

> 기본구문
````
<script>
    for (변수 선언문 또는 할당문; 조건식; 증감식) {
        조건식이 참인 경우 반복 실행될 문;
    }
</script>
````

````
 <script>
    // for (초기값 정의; 실행 조건; 갱신) { ... }
    for (let i = 0; i < 5; i++) {
        console.log(`현재 i의 값: ${i}`);
    }

    console.log('루프가 종료되었습니다.');
</script>
````

````
 <script>
    // 선언은 let으로 보통 합니다. (변수할당의 변화가 있을 때 대비)
    // 1부터 10까지 1씩 증가 반복문 
    for (let i = 0; i < 10; i++) {
        console.log(i)
    }

    // 증감값 2씩
    for (let i = 0; i < 10; i = i + 2) {
        console.log(i)
    }

    // 1에서 100까지 더하기
    let sum = 0;

    for (let i = 1; i <= 100; i++) {
        document.write(i, "<br>");
        sum = sum + i;
    }
</script>
````

````
 <script>
    document.write("<h3>폰트 사이즈 키우기</h3>");
    document.write('<p>문장을 작성합니다</p>');

    let size = 40;

    document.write('<span style="font-size:' + size + 'px;">');
    document.write('보여질 글자');
    document.write('</span>');

    for (let size = 10; size <= 35; size += 5) {
        document.write('<span style="font-size:' + size + 'px;">');
        document.write('보여질 글자' + size);
        document.write('</span>');
    }    
</script>
````

````
<script>
    for (let i = 0; i < 50; i++) {
        if (i % 3 === 0 || i % 5 === 0) {
            console.log("3의 배수와  5의 배수 출력", i)
        }
    }
</script>
````
````
<script>
    for (let i = 0; i < 100; i++) {
        if (i % 3 === 0 && i % 5 === 0) {
            console.log("15의 배수 출력", i)
        }
    }
</script>
````

## break문 
> + 반복문(for, for...in, for...of, while, do...while) 또는 switch문의 코드 블록을 탈출한다.
> + 중첩된 for문의 내부 for문에서 break문을 실행하면 내부 for문을 탈출하여 외부 for문으로 진입한다.

````
<script>
    // break : 반복문 탈출
    for (let i = 0; i < 10; i++) {
        if (i == 5) {
            break; // 반복문이 종료됨
        }
        console.log(i)
    }

    let sum = 0;

    for (let i = 0; i <= 10; i++) {
        if (sum > 10) {
            break;
        }
        console.log("i값 출력", i)
        sum += i;
    }
    console.log(sum); // 15
</script>
````

## continue문
> + 반복문의 코드 블록 실행을 현 지점에서 중단하고 반복문의 증감식으로 실행 흐름을 이동시킨다. break문처럼 반복문을 탈출하지는 않는다.

````
<script>
    // break : 반복문 탈출
    for (let i = 0; i < 10; i++) {
        if (i == 5) {
            break; // 반복문이 종료됨
        }
        console.log(i)
    } 
</script>
````

````
<script>
    let x = 6;
    console.log(x % 3 == 0); // 3의 배수

    // 1부터 10까지 1씩 증가 반복문
    for (let i = 1; i <= 10; i++) {
        if (i % 3 == 0) { //i값이 3의 배수 일 경우
            document.write("3의 배수 출력 ", i, "<br>");
        }
    }

    // 1부터 10까지 1씩 증가 반복문
    // 홀수만 뽑아 출력
    for (let i = 1; i <= 10; i++) {
        if (i % 2 == 0) { // i를 2로 나눈 나머지가 0 이라는 것은 짝수일 때를 의미함
            continue; // 짝수를 제외
        }
        document.write("짝수 제외 3의 배수 출력 ", i, "<br>");
    }
</script>
````

````
<script>
    let sum = 0, // 합산을 위한 변수선언
        i; // i변수를 선언했으나 초기값을 할당하지 않은상태

    for (i = 1; i <= 10; i++) {// 1~10까지
        if (i % 2 == 0) { // 2로 나눈 나머지가 0이라는 것=> 짝수일 때를 의미함
            console.log(i)
            continue;// 짝수제외한 홀수만 출력
        }
        document.write(i, " + "); // for문 돌면서 하나씩 출력 1,2,3,4,5,6,7,8,9,10
        sum += i;//for문 돌면서 하나씩 받은 숫자를 합산한다
    }

    // for문을 다 돌고 난 후 합산 출력
    document.write("합산된 값은 ", sum)
</script>
````

## 중첩 반복문
+ 중첩 반복문이란 반복문 안에 새로운 반복문이 들어가 있는 것을 말한다.
+ 중첩의 횟수에는 제한이 없다.
+ 반복문의 형태에도 제한이 없다. ex) for문 안에 while문 (O) while문 안에 for문 (O)
+ 바깥 for문의 변수 초기화는 중첩반복문에서 단 1회만 실행된다.

> 1) 밖에 있는 for문이 1회 실행될 때, 안에 있는 for문이 모든 반복을 실행한다.
> 2) 안에 있는 for문의 동작이 끝나면 다시 밖에 있는 for문이 1회 실행되는 것
> 즉 밖에 있는 for문이 8번 반복하고, 안에 있는 for문이 3번 반복하는 형태면 총 24회(8*3)반복한다.

````
<script>
    for (var i = 2; i < 10; i++) {
        for (var j = 1; j < 4; j++) {
            console.log(i + " x " + j + " = " + (i * j));
        }
    }
</script>
````

```
<script>
    // 표 만들기
    let table = "<table border='1'>";
    let num = 1

    for (let i = 1; i <= 10; i++) {
        table += "<tr>";
        for (let j = 1; j <= 10; j++) {
            table += "<td>" + num + "</td>";
            num++;
        }
        table += "</tr>";
    }

    table += "</table>";

    document.write(table);
</script>
````
## 템플릿 리터럴(Template Literal)
> + 템플릿 리터럴이란 자바스크립트에서 문자열을 입력하는 방식이다. 
> + 기존에는 var str = 'Hello ES6'와 같은 방식으로 사용하였으나 ES6에서는 백틱(back-tick)이라는 기호(`)를 사용하여 정의한다.
> + 백틱을 이용하게 되면 여러 줄에 걸쳐 문자열을 정의할 수도 있고, 자바스크립트의 변수를 문자열 안에 바로 연결할 수 있는 이점이 생긴다.
> + 문자열에 특정 변수의 값을 함께 사용하려면 +를 이용하여 문자열 중간에 해당 변수를 연결해줘야 했었으나
> + ES6에서는 템플릿 리터럴을 이용하면 아래와 같이 간편하게 문자열과 변수를 함께 사용할 수 있다.
> + ${ } 를 이용하면 위와 같이 변수의 값을 대입할 수 있을 뿐만 아니라 간단한 연산도 할 수 있다.

````
<script>
    for (let i = 1; i <= 6; i++) {
        for (let j = 1; j <= 6; j++) {
            if (i + j === 6) console.log(`[${i}, ${j}]`); // 백틱, 템플릿 문자열, 템플릿 리터럴
        }
    }
    /* 출력결과
    [1, 5]
    [2, 4]
    [3, 3]
    [4, 2]
    [5, 1]
    */
</script>
````

````
 <script>
    // 구구단
    for (let i = 2; i <= 9; i++) {
        document.write(i + '단')
        document.write('<hr>')
        for (let j = 1; j <= 9; j++) {
            document.write(i, ' * ', j, ' = ', (i * j))
            document.write('<br>')

            // 백틱, 템플릿 문자열, 템플릿 리터럴
            console.log(`${i} x ${j} = ${i * j}`)
        }
    }
</script>
````