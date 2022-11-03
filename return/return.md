# return

return의 주요기능

1. 함수로부터 하나의 데이터를 반환한다.
2. 함수를 끝낸다.

<br>

return 키워드는 함수안에서만 사용이 가능하며 함수를 호출한 부분으로 데이터를 전달해주기 위해서 사용한다.

<br>

***

<br>

인수와 매개변수에서 함수를 호출하는 시점에 함수가 선언된것으로 데이터를 전달한다.

함수를 호출할때 함수로 데이터를 전달하는 방법이 인수와 매개변수를 활용한 것이었으면

함수 안에서 함수를 호출한 쪽으로 데이터를 전달하는 방법이 return 키워드를 이용한 방법인 return문이다.

함수 호출 -> 함수 선언 (인수,매개변수 활용)
함수 선언 -> 함수 호출 (return 키워드 이용)

<br>

***

<br>

### 1. 데이터를 반환.

```javascript
function sum(number1,number2){
    return number1 + number2;
}

const sum_result_1 = sum(10, 20); //30
const sum_result_2 = sum(20, 30); //50

const sum_result = sum_result_1 + sum_result_2; //80

console.log("총 합은 " + sum_result + "입니다.");
```

위의 코드를 해석하면

함수 sum()은 인자 값으로 number1과 number2를 가지고 있으며, number1와 number2를 더하는 식을 함수 sum()에 반환(return) 한다.

따라서 const sum_result_1 = sum(10,20)는 함수 sum()에 인자 값으로 10과 20을 가진상태로 함수sum()을 호출하였으므로 앞서 함수 sum(number1,number2)이 호출될 때마다 return 뒤의 데이터(+)로 반환되기로 하였으니 sum(10+20)로 계산되어 sum_result_1의 값은 30으로 나온다.

sum_result_2역시 마찬가지고 인자 값으로 들어있는 20과 30이 더해져서 50이 나오는 것이다.

따라서 결과적으로
해당 코드를 실행해 보면

"총 합은 80입니다." 가 출력된다.

이처럼 return을 이용하여 함수안의 인자 값을 리턴으로 계산을 하고 


### 2. 함수를 끝낸다.
```javascript
function sayHi(){
    console.log("Hi")
    console.log("Hello")
    return;
    console.log("안녕") //리턴 뒤에서
}
sayHi() //함수 호출

//결과

//Hi
//Hello
```

단순히 return을 써두기만 하여도 함수를 끝낸다.

따라서 return뒤에있는 데이터 console.log("안녕")은 출력되지 않는다.

***
