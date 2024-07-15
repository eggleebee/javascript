# 01-배열과 자료구조
## 배열
+ 배열은 여러 자료를 묶어서 활용할 수 있는 특수한 자료구조로 여러 개의 변수를 한 번에 선언해 다룰 수 있는 자료형이다.
+ 배열은 순서가 있는 값으로 리스트와 비슷한 객체로, 순서가 있는 형태의 데이터를 담기에 용이하다.
+ 배열은 대괄호[…]를 사용해 생성하고 내부의 값을 쉼표(,)로 구분해 입력한다. 
+ 배열 내부에 들어 있는 값을 요소라한다. 
+ 배열의 길이와 요소의 자료형은 고정되어 있지 않다.(어떠한 종류의 자료형도 요소가 될 수 있음)

## 배열을 만드는 방법 2가지
+ 배열 리터럴 **대괄호[요소, 요소, 요소, … , 요소]** 를 사용하여 만드는 방법
+ **Array() 생성자 함수**로 배열을 생성하는 방법

### 배열 리터럴 **대괄호[요소, 요소, 요소, … , 요소]** 로 배열 생성

````
<script>
    // 빈 배열
    const nums = []
    nums[0] = 100
    nums[1] = 200
    nums[2] = 300
    console.log(nums)

    // 초기값 할당
    const colors = ['빨강', '노랑', '파랑']
    console.log(colors)
</script>
````

###  **Array() 생성자 함수**로 배열을 생성

````
<script>
    // 빈 배열
    var arr = new Array();
    arr[0] = 100;
    arr[1] = 200;
    arr[2] = "javascript";

    document.write(arr[0], "<br>");
    document.write(arr[1], "<br>");
    document.write(arr[2], "<br>");

    // 배열 생성 (초기 값 할당)
    var arr = new Array('zero', 'one', 'tow');

    for (let i = 0; i < arr.length; i++) {
        console.log(arr[i]);
    }

    // 배열 생성 (배열 크기 지정)
    // 원소가 1개이고 숫자인 경우 배열 크기로 사용됨
    var arr = new Array(3);

    for (let i = 0; i < arr.length; i++) {
        console.log(arr[i]); // 값이 할당되지 않아서 undefined 3번 출력  
    }
</script>
````

## 배열 요소에 접근하기
+ **배열[인덱스]**
+ 배열의 각각의 요소에 접근하려면 배열 바로 뒤에 대괄호[ ]를 입력하고 그 안에 숫자를 넣는다. 
+ 자바스크립트는 가장 앞에 있는 요소를 0번째로 표현한다. 
+ 이때 요소의 순서를 인덱스라고 부른다.

> + 배열의 순서 : 각 배열에는 순서가 생기는데 이를 index라고 한다. (index는 0부터 시작)
> + 배열의 이름 : 배열은 여러 개의 요소를 갖기 때문에 일반적으로 배열 이름을 복수형으로(number →numbers) 짓는다.

````
<script>
    // 배열 요소에 접근, 특정 요소만 뽑아내기
    const animals = ["원숭이", "사자", "호랑이"];

    console.log(animals[0]); //원숭이
    console.log(animals[1]); //사자
    console.log(animals[2]); //호랑이
</script>
````

## 배열 요소 개수 확인하기
+ **배열.length**
+ 배열 내부에 들어 있는 요소의 개수를 확인할 때는 배열의 **length** 속성을 사용한다. 
+ 배열 뒤에 점(.)을 찍고 length라고 입력해주면 된다.
+ 또한, length 속성 값을 직접 설정하여, 배열의 길이를 조정할 수도 있다.

````
<script>
    // 배열 크기 지정
    const array = [, , , ,]
    
    // 배열의 길이는 Array 인스턴스의 length 속성을 통해서 확인할 수 있다.        
    // 배열 요소 개수 확인하기 : 배열.length
    // 배열 요소에 접근하기 : 배열[인덱스]

    // 반복문을 이용하여 배열의 갯수만큼 모든 요소를 출력
    for (let i = 0; i < array.length; i++) {
        console.log(array[i]) // 값이 할당되지 않아서 undefined 4번 출력
    }

    // 배열의 크기를 임의로 변경
    // length 속성 값을 직접 설정하여, 배열의 길이를 조정할 수도 있습니다.
    array.length = 2;
    console.log(array.length)
    console.log(array) // [비어 있음 × 2]

    // 새로운 배열을 추가하면 크기는 자동으로 변경 
    array[5] = 'apple';
    console.log(array.length)
    console.log(array) // [비어 있음 × 5]

    // 새로운 배열 추가로 크기 변경
    array.push('banana');
    console.log(array.length)
    console.log(array) // [비어 있음 × 5, 'apple', 'banana']

    // 반복문을 이용하여 배열의 모든 요소를 화면에 출력
    for (let i = 0; i < array.length; i++) {
        document.write(array[i], "<br>");
    }
</script>
````

## 배열의 반복문
반복문을 이용하여 배열안의 값들을 하나씩 돌면서 전부 출력할 수 있다.

### for
````
<script>
    // 기본구조
    // for (조건) {실행문}

    const food = ['피자','콜라','치킨']
    console.log('음식 갯수', food.length) // 3
    console.log('음식 전체 출력', food)
    console.log('food[0] 출력', food[0])// 피자
    console.log('food[1] 출력', food[1])// 콜라
    console.log('food[2] 출력', food[2])// 치킨

    // 반복문으로 음식 갯수만큼 과일이름을 화면에 출력
    // i가 arr.length까지 i++(계속 더하며) 반복된다.
    // food[i] 번째 객체를 반복하여 콘솔출력
    // arr.length 번째까지 반복, 이후 종료
    for( let i = 0 ; i < food.length ; i++ ){
        console.log( food[i] )
    }
</script>
````

### 배열을 문자열로-join() 함수
+ 배열을 문자열로 바꿀 때 join() 함수를 사용
+ join() 함수는 배열의 모든 요소를 연결해 하나의 문자열로 만듭니다.
+ 구분자를 넣어주게 되면 문자열로 바뀔때 사이사이에 지정한 구분자가 들어간다.

````
<script>
    const arr = ["사과", "포도"]; 

    console.log('과일갯수', arr.length);
    const count = arr.length
    console.log('과일갯수 count변수 값 출력', count);

    const fruits = arr.join(" , ")

    // 반복문으로 과일갯수만큼 과일이름을 화면에 출력
    for ( let i = 0; i < fruits.length; i++ ) { /
        document.write(fruits[i]); 
    } 
</script>
````

### for of

````
 <script>
    let iterable = [10, 20, 30];

    // variable : 각 반복에 서로 다른 속성값이 variable에 저장됩니다.
    // iterable : 반복되는 열거가능(enumerable)한 속성이 있는 객체

    for (let variable of iterable) {
        console.log(variable);
    }

    let array = ['사자', '호랑이', '기린']
    console.log(array)
    console.log(array[0])
    console.log(array[1])
    console.log(array[2])

    // Object를 제외한 반복 가능한 iterable Object (Array, Map, Set, String)등을 순회.
    for (const element of array) {
        console.log('for of문으로 출력', element)
    }
</script>
````

## 문자열과 반복문 for와 for of

````
<script>
    let str = 'hello';

    // for 사용
    for (let i = 0; i < str.length; i++) {
        let txt = str[i]
        console.log("for 사용", txt)
    }

    // for ... of 사용
    for (let txt of str) {
        console.log("for ... of 사용", txt);
    }

    let iterable = "안녕하세요";

    for (let value of iterable) {
        console.log("for ... of 사용", value);
    }
</script>
````

### 문자열을 배열로-전개구문과 splict()함수 + 반복문 forEach
+ 문자열을 반복문 돌리고 싶을 경우 문자열은 Array가 아니어서 forEach 함수를 사용할 수 없다.
+ 문자열을 배열로 변환,spread operator(전개 구문)을 사용
````
 <script>
    // 전개구문
    const str = "문자열을 배열로 변환하기";
    const arr = [...str];
    console.log("배열인가?", Array.isArray(arr));
    console.log("하나씩 출력", arr);

    // forEach + 화살표 함수
    arr.forEach(strArr => console.log(strArr));
    // [...str].forEach(strArr => console.log(strArr));

    const sentence = "문자열을,배열로,변환후,forEach,함수를,사용";

    // split() 함수 : 문자열을 특정 구분자로 나누어 배열로 만든다.
    const words = sentence.split(",");

    [...words].forEach(function(wordsArr, index){
        console.log(wordsArr)
    });
</script>
````
### for in



### map

## 배열의 주요 메서드
### 요소를 더하거나 지우는 메서드
push
pop
shift
unshift
splice
splice
contact

### 원하는 요소 찾기 메서드
indexOF/lastIndexOf(item,pos)
includes(value)
find/filter(func) - func의 반환 값을 true로 만드는 첫 번째/정체 요소를 반환함
findIndex

### 배열전체순회하기
forEACH(func) 모든 요소에 func를 호출함. 결과는 반환되지 않음

### 배열 변형하기
map(func)
sort(func)
reverse()
split/jion
reduce

### 데이터 변경
> + push(): 배열의 끝에 값을 추가.
> + pop(): 배열 마지막 값을 제거.
> + shift(): 배열 데이터를 왼쪽으로 하나씩 밀어 맨앞 값을 제거.
> + splice(): 배열값을 추가하거나 제거해서 반환.
> + reverse(): 배열을 역순으로 재배치.
> + sort(): 배열 데이터를 정렬

## 배열의 일부를 반환
> + concat(): 두개의 배열을 합침.
> + join(): 배열 데이터 사이에 원하는 문자열을 넣어 구분자로 사용.
> + slice(): 배열의 일부을 지정해서 가져옴.

### 데이터 순회
> + map(): 모든 배열 데이터마다 반복 처리가 필요한 경우 사용.
> + filter(): 특정 조건을 만족하는 데이터만 처리할 경우 사용.
> + reduce(): 모든 데이터를 순화하면서 누적 연산이 필요한 경우 사용.

# 02-함수