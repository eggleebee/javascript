# 03-제어문
+ 제어문은 조건에 따라 코드 블록을 실행하거나 반복 실행할 때 사용한다. 
+ 일반적으로 코드는 위에서 아래방향으로 순차적으로 실행되는데, 제어문을 사용하면 코드의 실행 흐름을 인위적으로 제어할 수 있다.


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


> 조건문-if
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

> 조건문-if...else
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

### 조건식 거짓으로 취급하는 값
+ false
+ undefined 
+ null 
+ 0 
+ NaN 
+ the empty string ("")

````
 <script>
    // if 안의 조건문이 "참"이 아니기 때문에 else 문 실행
    if (false) {
        console.log("거짓")
    } else {
        console.log("참")
    }

    if (undefined) {
        console.log("거짓")
    } else {
        console.log("참")
    }

    if (null) {
        console.log("거짓")
    } else {
        console.log("참")
    }

    if (0) {
        console.log("거짓")
    } else {
        console.log("참")
    }

    if (NaN) {
        console.log("거짓")
    } else {
        console.log("참")
    }

    if ("") {
        console.log("거짓")
    } else {
        console.log("참")
    }
</script>
````

> 조건문-if...else-아이디 비밀번호 확인
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

> 조건문-if문 여러개
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

> 조건문-if-else...if
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

> 조건문-if-else...if-등급 구분
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

> 조건문-if-else...if-음료 선택
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

> 조건문-if-else...if-음식 선택
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

> 조건문-if문 중괄호 생략
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

> if문의 중첩-아이디 비밀번호
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

> if문의 중첩-아이디 비밀번호
+ if ()문이 거짓일 때, 다른 조건문을 비교하려고 할 때 사용하는 것이 else if () 이다.

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

> if문-비밀번호 개수가 6개 이상
````
<script>
    const password = prompt('새로운 비밀번호를 입력해주세요!');

    if (password.length >= 6) {
        console.log("비밀번호 길이가 충분합니다.");
    } else {
        console.log("비밀번호를 6자 이상 입력해주세요.");
    }
</script>
````

> if문-비밀번호에 공백의 유무
````
<script>
    const password = prompt('새로운 비밀번호를 입력해주세요!');

    if (password.indexOf(' ') === -1) {  // -1이 나온다면 공백을 찾지 못한경우 (공백 X) 
        console.log('비밀번호에 공백이 없습니다');
    } else {
        console.log('비밀번호에 공백이 있습니다. 수정이 필요합니다.');
    }
</script>
````

>  다중 조건문을 사용-비밀번호 개수가 6개 이상 + 비밀번호에 공백의 유무
````
<script>
    const password = prompt('새로운 비밀번호를 입력해주세요!');

    // 비밀번호 개수가 6개 이상인 경우
    if (password.length >= 6) {
        if (password.indexOf(' ') === -1) {  // -1이 나온다면 공백을 찾지 못한경우 (공백 X) 
            console.log('올바른 비밀번호 입니다.');
        } else {
            console.log('길이는 충분하나, 비밀번호에 공백이 있습니다.');
        }
    } else {
        console.log("비밀번호가 너무 짧습니다. 6개 이상으로 설정 바랍니다.");
    }
</script>
````

> if문의 중첩-시험 점수

````
<script>
    let score = 96;
    let lecture = "sports";

    if (lecture == "sports") {
        if (score >= 70) {
            console.log("통과여부 : pass");
            console.log("점수", score);
        }
        else {
            console.log("통과여부 : fail");
        }
    } else {
        if (score >= 90) {
            console.log("점수 : A");
        } else if (score >= 80) {
            console.log("점수 : B");
        } else if (score >= 70) {
            console.log("점수 : C");
        } else if (score >= 60) {
            console.log("점수 : D");
        } else {
            console.log("점수 : F");
        }
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
+ break는 switch의 중괄호를 빠져나가는 명령어다.
+ witch조건문은 break문을 만나기 전까지 조건값들을 비교하여 case문 혹은 default문을 실행한다. 

### switch문 장점 : 간결성, 가독성
+ switch 조건문은 if else if 조건식으로 변환할 수 있다.
+ 두 식을 비교해보면 switch 조건문이 조금더 간결하고 가독성이 높다.

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

> 조건문-switch-요일 확인
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

> 조건문-switch-url 확인
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
+ 입력 받은 값이 숫자인지 문자인지 상관없이 string 타입으로 입력된다. 
+ 따라서 입력받은 값이 숫자일 경우, number로 형 변환을 한 후에 연산을 하는 등의 추가적인 코드 작성에 있어 parseInt 함수는 유용하게 사용된다.

## parseInt 란?
+ 자바스크립트에 내장되어 있는 함수로, 말 그대로 문자열을 파싱하여 문자열에 포함된 숫자를 찾아서 number로 형변환을 시켜준다.

> 조건문-switch-나이 확인
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