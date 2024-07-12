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

## 배열 요소에 접근하기
+ **배열[인덱스]**
+ 배열의 각각의 요소에 접근하려면 배열 바로 뒤에 대괄호[ ]를 입력하고 그 안에 숫자를 넣는다. 
+ 자바스크립트는 가장 앞에 있는 요소를 0번째로 표현한다. 
+ 이때 요소의 순서를 인덱스라고 부른다.

> + 배열의 순서 : 각 배열에는 순서가 생기는데 이를 index라고 한다. (index는 0부터 시작)
> + 배열의 이름 : 배열은 여러 개의 요소를 갖기 때문에 일반적으로 배열 이름을 복수형으로(number →numbers) 짓는다.

## 배열 요소 개수 확인하기
+ **배열.length**
+ 배열 내부에 들어 있는 요소의 개수를 확인할 때는 배열의 **length** 속성을 사용한다. 
+ 배열 뒤에 점(.)을 찍고 length라고 입력해주면 된다.

## 배열의 반복문
반복문을 이용하여 배열안의 값들을 하나씩 돌면서 전부 출력할 수 있다.

### for
### forEach
### for in
### map

````
<script>
    // 초기값 할당
    const colors = ['빨강', '노랑', '파랑']
    console.log(colors)

    // 특정 요소만 뽑아내기
    let animals = ["원숭이", "사자", "호랑이"];

    console.log(animals[0]); //원숭이
    console.log(animals[1]); //사자
    console.log(animals[2]); //호랑이

    // 빈 배열
    const nums = []
    nums[0] = 100
    nums[1] = 200
    nums[2] = 300
    console.log(nums)

    // 배열 크기 지정
    const arr = [, , , ,]

    // 배열 요소 개수 확인하기 : 배열.length
    // 배열 요소에 접근하기: 배열[인덱스]
    // 반복문을 이용하여 배열의 갯수만큼 모든 요소를 출력
    for (let i = 0; i < arr.length; i++) {
        console.log(arr[i]) // 값이 할당되지 않아서 undefined 4번 출력
    }

    // 서로 다른 데이터 타입을 담을 수 있다.    
    var array = [123, '안녕하세요', true, function () { }, [123, 456], ['딸기', '바나나']]
    console.log(array)
    console.log(array.length) // 6

    // 배열의 크기를 임의로 변경
    array.length = 2;
    console.log(array)
    console.log(array.length)

    // 새로운 배열을 추가하면 크기는 자동으로 변경 
    array[5] = 'apple';
    console.log(array)
    console.log(array.length)

    // 새로운 배열 추가로 크기 변경
    array.push('banana');
    console.log(array)
    console.log(array.length)

    // 반복문을 이용하여 배열의 모든 요소를 출력
    for (var i = 0; i < array.length; i++) {
        document.write(array[i], "<br>");
    }
</script>
````

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

    for (var i = 0; i < arr.length; i++) {
        console.log(arr[i]);
    }

    // 배열 생성 (배열 크기 지정)
    // 원소가 1개이고 숫자인 경우 배열 크기로 사용됨
    var arr = new Array(3);

    for (var i = 0; i < arr.length; i++) {
        console.log(arr[i]); // 값이 할당되지 않아서 undefined 3번 출력  
    }
</script>
````

https://velog.io/@promotion_dev/Javascript-%EB%B0%B0%EC%97%B4%EA%B3%BC-%EB%B0%98%EB%B3%B5%EB%AC%B8

https://hongong.hanbit.co.kr/javascript-%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EB%B0%B0%EC%97%B4-%EC%83%9D%EC%84%B1-%EC%9A%94%EC%86%8C-%EC%B6%94%EA%B0%80%EC%99%80-%EC%A0%9C%EA%B1%B0/

https://9silvery2.gitbook.io/javascript/javascript/undefined-2

https://dinfree.com/lecture/frontend/123_js_2.html#m5

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

## 배열전체순회하기
forEACH(func) 모든 요소에 func를 호출함. 결과는 반환되지 않음

## 배열 변형하기
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