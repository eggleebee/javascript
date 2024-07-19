# 03-제어문
+ 제어문은 조건에 따라 코드 블록을 실행하거나 반복 실행할 때 사용한다. 
+ 일반적으로 코드는 위에서 아래방향으로 순차적으로 실행되는데, 제어문을 사용하면 코드의 실행 흐름을 인위적으로 제어할 수 있다.

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

> for 구문
````
<script>
    // for (초기값 정의; 실행 조건; 갱신) { ... }
    for (let i = 0; i < 5; i++) {
        console.log(`현재 i의 값: ${i}`);
    }

    console.log('루프가 종료되었습니다.');
</script>
````

## 템플릿 리터럴(Template Literal)
+ 템플릿 리터럴이란 자바스크립트에서 문자열을 입력하는 방식이다. 
+ 기존에는 var str = 'Hello ES6'와 같은 방식으로 사용하였으나 ES6에서는 백틱(back-tick)이라는 기호(`)를 사용하여 정의한다.
+ 백틱을 이용하게 되면 여러 줄에 걸쳐 문자열을 정의할 수도 있고, 자바스크립트의 변수를 문자열 안에 바로 연결할 수 있는 이점이 생긴다.
+ 문자열에 특정 변수의 값을 함께 사용하려면 +를 이용하여 문자열 중간에 해당 변수를 연결해줘야 했었으나
+ ES6에서는 템플릿 리터럴을 이용하면 아래와 같이 간편하게 문자열과 변수를 함께 사용할 수 있다.
+ ${ } 를 이용하면 위와 같이 변수의 값을 대입할 수 있을 뿐만 아니라 간단한 연산도 할 수 있다.


> 1부터 10까지 증감값 2씩
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
</script>
````

> 1에서 100까지 더하기
````
<script>
    let sum = 0;

    for (let i = 1; i <= 100; i++) {
        document.write(i, "<br>");
        sum = sum + i;
    }
</script>
````

> 폰트사이즈 키우기
````
<script>
    document.write("<h3>폰트사이즈 키우기</h3>");
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

> for문 안에 if문-3의 배수와 5의 배수
````
<script>
    for (let i = 0; i < 50; i++) {
        if (i % 3 === 0 || i % 5 === 0) {
            console.log("3의 배수와 5의 배수 출력", i)
        }
    }
</script>
````

> for문 안에 if문-15의 배수
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
+ 반복문(for, for...in, for...of, while, do...while) 또는 switch문의 코드 블록을 탈출한다.
+ 중첩된 for문의 내부 for문에서 break문을 실행하면 내부 for문을 탈출하여 외부 for문으로 진입한다.


> 반복문 제어-break
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
+ 반복문의 코드 블록 실행을 현 지점에서 중단하고 반복문의 증감식으로 실행 흐름을 이동시킨다. break문처럼 반복문을 탈출하지는 않는다.

> 반복문 제어-continue 
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

> 반복문 제어-continue-3의 배수 
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
</script>
````

> 반복문 제어-continue-짝수 제외 홀수만 출력
````
<script>
    // 1부터 10까지 1씩 증가 반복문
    // 홀수만 뽑아 출력
    for (let i = 1; i <= 10; i++) {
        if (i % 2 == 0) { // i를 2로 나눈 나머지가 0 이라는 것은 짝수일 때를 의미함
            continue; // 짝수를 제외
        }
        document.write("짝수 제외 홀수만 출력 ", i, "<br>");
    }
</script>
````

> 반복문 제어-continue-홀수만 합산
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


> 중첩 for문
````
<script>
    for (var i = 2; i < 10; i++) {
        for (var j = 1; j < 4; j++) {
            console.log(i + " x " + j + " = " + (i * j));
        }
    }
</script>
````

> 중첩 for문-표만들기
````
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

> 중첩 for문-템플릿 리터럴
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

> 중첩 for문-구구단
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