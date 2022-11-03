# Object 객체

## Object 는 객체이다.

객체는 여러종류의 데이터를 묶음으로 관리하는 데이터 타입이다

array는 대괄호로 시작한 반면 object는 중괄호로 시작하고 key들이있고
그 key 들에 해당하는 데이터가 있다.

```javascript
let myself = {
    name: 'Dave Ahn',
    location: {
        country: 'South Kore',
        city: 'Seoul'},
    age: 30,
    color: ['blue', 'red']
    }
```

myself라는 변수에 다음과 같은 객체가 할당되어있다.

name 이라는 "key" 에 Code Kim이라는 데이터가 매치되어있고
location이라는 key에는 또 다른 객체가 매치가 되어있다.

<br>

그 location 이라는 key안에 country 라는 key 안에 South Korea라는 데이터가 매치되어있고 city 라는 key 안에 Seoul이라는 데이터가 매치되어있다.

<br>

그다음은 age라는 key에는 30이라는 데이터가 매치되어있고
그리고 마지막으로 color라는 key에는 array (배열)이 데이터로 묶여있다.

<br>

***

<br>

# Property 프로퍼티

<br>

array에 포함되어있던 데이터 하나하나는 "요소"라고 불렀다.

객체에 포함되어있는 데이터는 <i>"property"</i> 라고 부른다.

위 myself라는 변수에는 'name' , 'location' , 'age' , 'cat' 이 4개의 <i>property(프로퍼티)</i> 가 있는것이고

이 property는 key와 value로 이루어져있다.
'name' , 'location' , 'age' , 'cat' 객체에 프로퍼티가 가지고있는 key라고 부른다.

그리고 key에 하나하나 대응하는 데이터를 <i>"value"</i>라고 부른다.


```javascript
let myself = {
    name: 'Dave Ahn'
    }
```

위의 변수 myself의 객체를 읽을때는<br>
<h2>변수 myself의 객체 중 name 이라는 key의 value는 'Dave Ahn' </h2> 라고 한다.

<br>

***

<br>

# 출력과 순서


```javascript
let myself = {
    name: 'Dave Ahn',
    location: {
        country: 'South Kore',
        city: 'Seoul'},
    age: 30,
    color: ['blue', 'red']
    }

console.log(myself)

```

위 변수 myself를 출력해보면

```javascript
{name: 'Dave Ahn', location: {…}, age: 30, color: Array(2)}
age: 30color: (2) ['blue', 'red']
location: {country: 'South Kore', city: 'Seoul'}
name: "Dave Ahn"
[[Prototype]]: Object
```

위 처럼 표시된다.

각각의 프로퍼티가 출력되었는데, 객체에 넣은 순서대로 출력되지 않은것을 확인 할 수있다.

자바스크립트 내부적으로 <u>object를 저장할때 property의 순서까지 같이 저장하지는 않는다.</u>

그래서 <u>객체에 넣은 순서대로 property가 출력되는게 아니다.</u>

순서가 없다.

<br>

<i>index가 없다.</i>

<br>

0번째 1번째 이런 순서가 없어서 순서가 뒤죽박죽 나오게된다.

<br>

***


<br>

# 객체에 저장된 데이터에는 어떻게 접근을 하는가?

array같은 경우는 index번호로 접근이 가능했다.
<br>

<br>

(예 : myarray 0번째 index)

<br>

객체에서는 <u>key를 이용해서 value에 접근하는 방식으로 object를 이용</u>한다.

<br>

크게 두가지 방법이 있다.

<br>

<br>

## 1. Dot Notation
객체의 이름에다 . (점) 을 찍고 접근하고자 하는 key를 입력하면 value를 얻을 수 있다.

```javascript
let myself = {
    name: 'Dave Ahn',
    location: {
        country: 'South Kore',
        city: 'Seoul'},
    age: 30,
    color: ['blue', 'red']
    }

console.log(myself.name)
```

위 처럼 console.log(myself.name) 을 출력하면
key name 의 value인 Dave Ahn이 출력된다.

위 변수 myself의 key중 location은 객체 속의 객체이다.

location을 출력하면 어떻게 될까?

```javascript
let myself = {
    name: 'Dave Ahn',
    location: {
        country: 'South Kore',
        city: 'Seoul'},
    age: 30,
    color: ['blue', 'red']
    }

console.log(myself.location) //{country: 'South Kore', city: 'Seoul'}
```

{country: 'South Kore', city: 'Seoul'}
위처럼 객체 자체가 출력된다. (객체 속 Array도 마찬가지로 똑같이 출력된다.)

<br>

<br>

## 2. Bracket Notation

똑같은 객체가 있다고 가정했을때 괄호를 이용해서 접근하는 방법이다.

myself['name'] // Dave Ahn

위 처럼 객체 이름 뒤에 대괄호[]를 열어주고 접근하고자 하는 key를 따옴표'' 를 이용하여 접근하면 출력된다.


```javascript
let myself = {
    name: 'Dave Ahn',
    location: {
        country: 'South Kore',
        city: 'Seoul'},
    age: 30,
    color: ['blue', 'red']
    }

console.log(myself['name']) //Dave Ahn
```

위처럼 key에 접근하는 방법으로 변수에 할당 할 수도있다.

```javascript
let myColor =  myself['color']
console.log(mycolor)

//출력 : ['blue', 'red']
```

***
<br>

# Dot Notation과 Bracket Notation의 차이점

스샷 첨부

<br>

### __프로퍼티의 키에 변수가 포함되어있으면 Dot notation으로는 접근을 할 수가 없다.__

```javascript
let myself = {
    name: 'Dave Ahn',
    location: {
        country: 'South Kore',
        city: 'Seoul'},
    age: 30,
    color: ['blue', 'red']
    }


let myKey = 'color'

console.log(myself['color']) //['blue', 'red']
console.log(myself[myKey]) //['blue', 'red']
```
위처럼 출력하면 똑같은 value가 두 번 출력된것이다.

color라는 텍스트가 myKey라는 변수에 담겨있기때문에
myKey를 출력하면 'color' 를 넣은것과 같아지기때문에
key 'color'의 value인 ['blue', 'red'] 가 출력된다.

<br>

**이 방식은 Dot Notation으로 객체에 접근할때는 변수를 사용 할 수 없다.**

```javascript
console.log(myself.myKey) // undefined
```
위처럼 Dot Notaion으로 myKey라는 변수를 사용해서 접근하면
undefined가 나온다.

그렇다면 만약에 변수 myself의 객체 안에 myKey라는 Key자체가 있고 value값도 지정되어있으면 어떻게 될까?

<br>

아래 예제를 보자.

```javascript
let myself = {
    name: 'Dave Ahn',
    location: {
        country: 'South Kore',
        city: 'Seoul'},
    age: 30,
    color: ['blue', 'red']
    myKey: 'Hello Key'
    }


let myKey = 'color'

console.log(myself['color']) //['blue', 'red']
console.log(myself[myKey]) //['blue', 'red']

console.log(myself.myKey) //"Hello Key"
```

위처럼 Dot Notation은 변수를 사용 할 수없다.
그래서 " . " 뒤에 myKey라는 값이 왔을때 변수라고 생각하지 않고 object 안에 들어가있는 myKey라는 key를 찾아가서 그 key가 가르키고있는 value인 Hello Key를 출력하게 된다.

<br>

### __존재하지 않는 key__


```javascript
let myself = {
    name: 'Dave Ahn',
    location: {
        country: 'South Kore',
        city: 'Seoul'},
    age: 30,
    color: ['blue', 'red']
    myKey: 'Hello Key'
    }


let myKey = 'color'

console.log(myself['color']) //['blue', 'red']
console.log(myself[myKey]) //['blue', 'red']

console.log(myself.yourKey) //undefined
```

자바스크립트 object는 위처럼 존재하지 않는 키(yourKey)에 접근하면 undefined가 뜬다.

<br>
<br>

2022.10.03 18:23 Dave Ahn

