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





       





   


