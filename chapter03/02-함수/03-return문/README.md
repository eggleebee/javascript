# 02-함수
# 02-03-return문

## 반환값(return)
+ 함수는 필요에 따라 결과값을 반환할 수 있다. 
+ 함수 내에서 return 키워드를 사용하여 반환하고자 하는 값 또는 표현식을 지정한다. 
+ 함수에서 return 키워드로 실행 결과를 외부로 반환할 수 있다.
+ 반환된 값은 함수를 호출한 곳으로 전달되며, 이를 이용하여 다른 작업을 수행할 수 있다.
+ return뒤에 오는 값, 표현식을 평가해 반환할 수 있다. 
+ 반환되는 즉시 함수 실행이 끝난다.

````
<script>
    function add(x, y) {
        return x + y;
        console.log('이 부분은 실행되지 않습니다.');
    }
    add(1, 2); // 3
</script>
````

> 매개변수+리턴 활용-자판기에서 음료수 꺼내기

````
<script>
    function 자판기(종류){
        return 종류
    }
    var data = 자판기("콜라") +'가 나왔습니다';
    document.write(data) //콜라가 나왔습니다
</script>
````

> if 구문 내부 return문

````
<script>
    function doSomething () {
        console.log('함수실행!');
        var a = 3;
        var b = 2;

        // if 구문 내부가 실행되면서 return 명령문이 실행됐기 때문에 return 명령문은 해당 함수를 종료시키게 된다. 
        // 현재 return 명령문이 속해있는 함수는 doSomething이기 때문에 doSomething함수의 모든 코드 실행이 종료됨으로 
        // 세번째 콘솔 메시지는 나타나지 않는다.
        if (a > b) {
            console.log('a가 b보다 크다!');
            return;
        }

        return 3;

        console.log('세번째 콘솔 메시지!'); //실행되지 않음
    }

    doSomething(); // 결과 : 함수실행!, a가 b보다 크다!
</script>
````

