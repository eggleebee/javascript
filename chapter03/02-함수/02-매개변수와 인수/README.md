# 02-함수
# 02-02 매개변수와 인수

## 매개변수(parameter)
+ parameter = 매개변수 = 변수
+ 함수 이름 옆에 () 소괄호 내부에 들어간다. 
+ 매개변수는 함수 선언에서 지정한 변수로, 함수의 기능을 수행하기 위해 필요한 값들을 받아들인다. 
+ 선언 시 매개변수 목록을 정의하면 함수를 호출할 때 인자값을 전달할 수 있다.
+ 매개변수가 없는 함수도 존재한다.
+ 매개변수 개수가 정해져 있지 않기 때문에 자바스크립트에서는 넘어오는 매개변수 값을 저장할 수 있는 저장장소 'arguments'라는 객체를 제공해준다.


> 매개변수-자판기에서 음료수 꺼내기

````
<script>
    function 자판기(음료수){
        document.write(음료수 + "가 나왔다.<br>"); 
    }

    자판기("사이다");
    자판기("콜라");
</script>
````

> 매개변수-자판기에서 음료수 일정 수량 꺼내기

````
<script>
    function 자판기(음료수, 수량){
        document.write( 음료수 + ' ' + 수량 + "개 나왔습니다"); 
    }

    자판기("사이다", 3);
</script>
````

> 매개변수-숫자더하기

````
<script>
    function plusNumber(a,b) {  // 매개변수 a, b 
        return console.log(a+b);
    }

    plusNumber(40,50)
</script>
````

> 매개 변수 값으로 객체, 배열도 전달 가능

````
<script>
    let fruit = ["딸기", "포도", "바나나"]
    let person = { name: "홍길동", age: 20, job: "회사원" }

    function printValue(arr, obj) {
        console.log(arr[0] + "\n")
        console.log(obj.name)
    }

    printValue(fruit, person)
</script>
````

## 인수(argument)
+ argument = 전달되는 값
+ 인수는 함수를 호출할 때 전달되는 값으로, 매개변수와 대응된다. (매개변수와 인수는 개수와 순서가 동일)
+ 매개변수보다 적은 인수가 들어오는 경우 전달되지 않은 부분은 undefined가 된다. 
+ 매개변수보다 많은 인수가 들어오는 경우 초과된 인수는 내부적으로 arguments라는 객체로 저장되어 보관된다.

> 전달되는 값(인수)

````
<script>
    const x = 2;
    const y = 3;

    function add(a, b) { // 매개변수 a, b 
        return a + b;
    }

    const result = add(x, y); // 전달되는 값(인수) x = 2, y = 3
</script>
````

> arguments 개수확인

````
<script>
    function func(a, b, c) {
        console.log(arguments);
        console.log(arguments.length); // arguments 개수확인
    }

    func(10, 20, 30)
</script>
````

> 매개변수보다 적은 인수가 들어오는 경우

````
<script>
    function add(x, y) {
        return x + y;
    }

    add(3) // NaN = 3 + undefined
</script>
````

> 매개변수보다 많은 인수가 들어오는 경우

````
<script>
    function add(x, y) {
        return x + y;
    }

    add(5, 10, 15) // 15 = 5 + 10  *3번째 인수 15는 arguments객체에 저장됨
</script>
````


