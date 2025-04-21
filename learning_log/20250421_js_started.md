

# JavaScript   

## 실습 환경 구축하기
1. window + 기본이라고 검색 -> 기본앱 -> 웹브라우저를 크롬으로
2. JS_sql_study 폴더 우클릭 -> js_study 생성
3. ch01 폴더 생성4



#### HEllo, JavaScript
- console창에 출력하는 명령어
```js
console.log('Hello, JavaScript');
```

## Consola과 주석 사용하기
### 콘솔
- 최종 사용자가 아닌 개발자를 위한 메시지 출력을 목적으로, 주로 개발 도중에 중간 결과를 확인하고, 디버깅을 위해 사용되는 영역.

Java에서는 %d을 사용하지 않으면 저렇게 작성해야하는 데 반해서,
```js
console.log(1,2,3);   // 결과값 : 1 2 3 -> 자료형은 number
```
즉 콘솔 기능의 장점은 괄호 내에 쉼표(,)을 이용하여 여러 데이터를 한 번에 출력 가능하다는 점입니다.
### 주석(Comment)
- 모든 프로그래밍 언어에서 활용하는 개념으로, 컴퓨터가 무시하는 메시지.
- // : JavaScript에서의 주석 방법
- /**/ : 다중 주석
- ctrl + / : 일단 코드 써놓고 사후 주석처리 방법

## 변수와 상수에 데이터 담기

## 변수와 상수
1. 변수 
  - 값을 지정하고 '변경이 가능한 것을' 변수
2. 상수
  - 값을 저장하지만 '변하지 않는 고정된 값'을 담는 것을 상수

```js
let darkModeOn = true;
const PI = 3.1415926535;
console.log(PI); // 결과값 : 3.1415926535
console.log(darkModeOn); // 결과값 : true
darkModeON = false;
console.log(darkModeOn); // 결과값 : false
PI = 5;   // 상수에 값을 재대입했으므로 오류 발생
```

* 예전에는 변수를 선언할 때 var를 썼음.
  - ES6 이전에는 JS에서 변수를 선언할 때 var를 사용했습니다. 근데 ES6버전 이후에는 let과 const가 var를 대체 했음.

```js
// 여기가 코드의 처음이라고 가정합니다.
console.log(b);     // 원래 오류 발생해야함. 변수 b는 없으니까
var b = 3;          // 근데 var로 선언됐기 때문에 오류가 발생하지 않고 
                    // 67번 라인에 3이 아니라 undefined인 이유는
                    // b에 3이라는 데이터가 저장된 시점이 68번 라인이기 때문
                    // 근데 이상한 점은 변수 선언도 68번 라인이라는 점입니다.
                    // 그게 JS가 일관성 없는 프로그래밍언어인 이유였습니다.
                    // 이상을 해결하기 위해 let / const가 등장했습니다.
console.log(a);     // 얘도 67번 라인과 차이가 없어보입니다.
let a = 1;          // 여기가 차이가 생겨서 74번 라인은 바로 오류가 발생합니다.
                    // let을 쓰게 되면 Java에서처럼 '순서대로' 변수의 선언 및 초기화가 일어납니다.
```

1. let
 - let a = 1; 에서 우리가 알 수 있는 점
    - let은 자료형과 관계없이 '변수'임을 명시한다는 점
    - a는 변수명(camel case로 작성)
    - =는 대입연산자라는 점
    - = 뒤에 데이터가 온다는 점
    - 재 대입의 경우에는 Java에서처럼 let을 명시하지 않는다는 점
```js
let studentName = '안근수';   // 변수 선언 및 초기화
console.log(studentName);   // 결과값 : 안근수
studentName = '김일'        // 선언된 변수에 데이터 재대입 -> let 명시 x
console.log(studentName);   // 결과값이 : 김일
```

```js
let a = 1;
console.log(a);       // 결과값 : 1
let b = a;  
console.log(a, b);    // 결과값 : 1 1
a = 2;                               // 프로그램은 '순서대로' 실행됩니다.
console.log(a, b);    // 결과값 : 2 1
```

* JS가 var에서 벗어났더니 또 골치아픈 점
- Java의 경우에는 처음 변수를 선언할 때 자료형을 명시하기 때문에 재 대입이 일어나느 과정에서 동일한 자료형이 아니면 오류가 발생했었습니다. 그런데 JS의 경우 let / const로 변수인지 상수인지만 명시하기 때문에 자료형이 다른 데이터를 변수에 대입하더라도 대입 상에서 오류가 발생하지 않습니다.
- 이상의 경우가 개발자 입장에서 변수 개수를 줄이면서 데이터를 바꿀 수 있으니 좋다고 생각하실 수도 있는데 예를 들어 input 태그에 type을 number로 잡아놔서 수학 연산을 하려고 했는데 거기에 string 자료형이 들어오게 되면 페이지에 오류가 발생할 수 밖에 없습니다. 그런데 대입 자체까지는 오류가 발생하지 않기 때문에 개발자들이 어느 부분에서 오류가 발생했는지 정확하게 파악하기 힘들다는 점이 문제였습니다.

```js
let a = 1;
console.log(a);       // 결과값 : 1
let b = a;  
console.log(a, b);    // 결과값 : 1 1
a = 2;                               // 프로그램은 '순서대로' 실행됩니다.
console.log(a, b);    // 결과값 : 2 1
a = '안녕하세요';     // 원래 정수에 string 자료형을 대입함 -> 오류 발생 x
b = true;           // 원래 정수에 boolean 자료형을 대입함 -> 오류 발생 x
console.log(a, b);  // 결과값 : 안녕하세요 ture 
```
## 기본 자료형 / 연산자

### 자료형

1. boolean 
-  참 / 거짓 여부 true / false
```js
let bool1 = true;
let bool2 = false;
console.log(bool1, bool2);
console.log(typeof bool1);    // 연산자 typeof : 변수의 자료형을 반환함.ㄴ
```
- typeof 기억하기

- number
  - int, long, float, double이 아니라 number 하나로 퉁쳤습니다.
```js
let num1 = 10;
let num2 = 3.14;
console.log(typeof num1, typeof num2);
```
  - number 자료형은 사칙 연산이 가능. 숫자 리터럴끼리의 연산도 가능하고, 리터럴과 변수 또는 상수 간의 연산도 가능.

  * 리터럴(literal) - 변수에 들어있지 않은 순수 데이터
```js
let a = 1;
console.log(a + 2);   // 라고 했을 때 2가 리터럴에 해당 -> 하드코딩이라서 지양.
```
  - 연산 종류
    1. +
    2. -
    3. *
    4. / 
    5. !
    6. %

- string
  - 문자열 자료형.
  - C / Java에서는 ''인지 ""인지에 따라서 문자와 문자열을 구분하는데, JS에서는 구분하지 않습니다.
  - 근데 관행상 HTML에서는 ""를 쓰고, JS에서는 ''를 씁니다.
  - string에서는 + 연산이 가능.
```js
let str1 = '안녕';
let str2 = '🍔';
console.log(str1 + '하세요' + str2);
```

- defined / null
  - undefined
    - 변수에 어떤 데이터가 들어가있는지 명시되지 않은 상태
  - null
    - 변수가 비어있는 상태로 저장되어있음.

```js
let x;                      // 변수의 선언 o / 초기화 x
console.log(x, typeof x);   // 결과값 : undefiend 'undefined'

x = 1;                      // 변수의 초기화
console.log(x);             // 결과값 : 1
x = null;
console.log(x, typeof x);   // 결과값 : null 'object'
```
특정 데이터의 자료형이 null인지는 확인이 불가능하고 x === null; 같이 추가적으로 코드를 작성해야한다는 문제점이 있습니다.

왜 object로 뜨는가 ?
- JS 자체가 떔질해가면서 만든 언어다보니까 초기 설계가 부실해서 최상위 계층인 object로 뜨는겁니다.

그렇다면 추후 사후 보강하면 되지 않는가?
- JS가 원래는 웹사이트에서 사용하는 언어이다보니까 근본을 전부 바꾸어버리면 JS기반으로 만든 웹사이트들이 전부 문제가 생깁니다. 그래서 기존의 문법을 바꾸는 대신에 더 좋은 기능을 추가해서 앞으로 개발할 때는 새로운 것을 허용하도록 하는 형태를 장려하고 있습니다.
  - let / const 가 생겼는데 여전히 var가 있는 이유를 생각하시면 됩니다.

### 연산자

- 이상까지 배운 연산자 + - * / ! % typeof입니다.
- 비교 연산자
  - 왼쪽과 오른쪽에 있는 항목을 비교한 값을 'boolean' 타입으로 반환하는 연산자
  - == - 자료형에 관계없이 같은(값으로 치환될 수 있는) 값
  - != - ==의 반대
  - === - 자료형도 같고 값도 같은 상태
  - !== - ===의 반대

```js
const a = '1';    // string
const b = 1;      // number
const c = '1';    // string
const d = 2;      // number

console.log(a == b, a != b);
console.log(a == c, a != c);
console.log(a == d, a != d);
console.log(a === c, a !== c);
console.log(a === b, a !== b);
```
  - `>`
  - `<`
  - `>=`
  - `<=` 

```js
let str1 = '안녕';
console.log(str1 === '안녕');
```
JS가 근본없다고 하는 이유 하나 더
```js
const str1 = 'ABC';
const str2 = 'DEF';

console.log(str1 === 'ABC');    // 결과값 : true
// 문자열의 경우에 사전 순서상 뒤로 오는 쪽이 더 크다고 인식함.
console.log(str1 > str2, str1 < str2);  // 결과값 : false true
```

- 부수 효과를 일으키는 연산자
  - 연산자를 사용했는데 변수의 값이 바뀌는 애들.
  - 변수++
  - 변수--
  - ++변수
  - --변수

- 할당 산술 연산자
  - x += y
  - x -= y
  - x *= y
  - x /= y
  - x %= y
  - x **= y     - x 값을 y만큼 제곱한 값을 구함.

```js
let x = 3;
x += 2;
console.log(x); // 결과값 : 5

x -= 3;
console.log(x); // 결과값 : 2

x *= 12;
console.log(x); // 결과값 : 24

x /= 3;
console.log(x); // 결과값 : 8

x %= 5;
console.log(x); // 결과값 : 3

x **= 4;
console.log(x); // 결과값 : 81(제곱)
```
- string은 +=이 가능합니다 .나머지는 불가능

- boolean 관련 연산자(논리 연산자)
  - && - AND
  - || - OR


- 삼항 연산자
형식
```js
(조건) ? (참일 때 출력할 값) : (거짓일 때 출력할 값);
let num1 = 103247;
console.log('num은 3의 배수에 해당' + (num1 %= 3 === 0?) '합니다' : '하지않습니다');
```

## JS 연산자 과제
- BMI 계산기를 작성하세요.
Scanner 형태로 받는 것이 아니라
let height = 172.5;
let weight = 68.7;

let bmi;
여러분이 BMI 계산식을 검색하든, Java에서 작성한걸 찾아보든 기타 등등 다양한 방식을 이용하여
실행 예

당신의 BMI지수는 ??.???? 입니다.
가 출력될 수 있도록 작성하시오.

```js
let height = 166.8;
let weight = 67.3;
let bmi;        // 아직 대입 안 시킬거니깐 선언만'
let answerBmi;
// 일단 height가 cm이기 때문에 m로 바꿔줘야 함
height /= 100;  // JS에서 배운거
bmi = weight / (height**2);
answerBmi = '당신의 BMi지수는 ';

console.log(answerBmi, bmi, '입니다.');
```
이상과 같은 방식 등으로 풀이가 가능합니다(다양한 방법의 풀이가 있을 수 있는데 오늘 배웠던 것을 최대한 사용하기 위해 사용한 방법)

여기서 중요한 점은 console.log();에 다양하 자료형의 데이터를 한꺼번에 작성하기 위해서는 '+', 혹은 ','가 연결되어 있어야 해서 불편합니다
  -> Java를 배운 저희는 그냥 그러려니 하고 작성했었지만 다른  Frontend 개발자들은 저 개념을 좀 싫어했습니다.
    그래서 다양한 자료형을 한 번에 넣더라도 +dhk , 로 연결하지 않는 방법을 고안했는데, 그것이백틱(`)을 이용한 방법입니다.

형식
```js
console.log(`어쩌고저쩌고한 스트링 데이터 : ${JS변수명}`);
```
으로 쓰게 될 경우 스트링 데이터와 JS 변수를 연결할 필요 없이 {} 내부 영역이 외부에 있는 변수를 참조한다는 것을 명시해줌으로써 가독성을 향상시켰습니다.
비슷한 경우가 python 등에서도 나타나기 때문에 알아두시는게 향후 좋습니다.

## 객체와 배열

### 객체(Object)
- 이상에서 배운 number, string, boolean 등의 자료형을 기본 자료형(Primitive types)이라고 했습니다. 즉, 각 자료형이 단 하나의 데이터만 가지고 있는 형태에 해당함.
- 이제 데이터 여러 개를 함께 묶어서 사용하는 복합 자료형도 사용하는데, 기본 자료형 외의 모든 데이터가 해당됨.
- 그 중에서 객체(Object)는 '키:값'의 형태로 이루어져있고, 이를 프로퍼티(property)라고 함.

형식
```js
const person1 = {
  name : '김일',
  age : 20,
  married : false,
};
console.log(typeof person1, person1);
```
java와의 대조
```java
@ALLArgsConstructor
class person {
  String name;
  int age;
  boolean married
}

public class PersonMain {
  public static main(args[]) {
    Person person1 = new Person("김일", 20, false);
  }
}
```

- 객체 접근 방법
형식
  1. 객체명.키이름
  2. 객체명['키이름']
```js
// # 1번째 방법
person1.name
// # 2번째 방법
person1['name']
```
- 근데 지금 보니까 # 2번째 방법은 좀 귀찮아보입니다. 왜 쓸까요 ?
  - 여러 명이서 협업을 하게 되는 경우가 많을텐데, 코드를 작성할 때 어떤 키 값이 들어오게 될지 모를 때가 많습니다. 예를 들어서 프로그램 실행을 하고 나서 input을 통해서 key 값을 집어넣게 된다고 하면 # 1번째 방법과 같은 방법으로는 코딩이 불가능합니다.

Java 기준으로 생각해보겠습니다.
```java
@ALLArgsConstructor
class person {
  String name;
  int age;
  boolean married
}

public class PersonMain {
  public static main(args[]) {
    Person person1 = new Person("김일", 20, false);

    Scanner scanner = new Scanner(System.in)
    System.out.print("검색하고자 하는 조건을 입력하세요 >>>")
    String key1 = scanner.nextLine();   // 그리고 실행시에 여러분이 married라고 쳤다고 가정

    System.out.println("김철수의 결혼 여부는 " + person.key1 + " 입니다.");
  }
}
```
java적으로 풀기는 했지만 이상의 코드가 오류가 발생한다는 점입니다.
person.key1 =/= person1.married이기 때문입니다.

그런 이유로 JS에서는 # 1번 방법, # 2번 방법 두 가지 방식의 value 접근법이 존재합니다.
두 가지 방법을 전부 다 알고 있어야 합니다.

```js
const person1 = {
  name : '김일',
  age : 20,
  married : false,
};

const person1Age = person1.age;   // 객체 property의 value값을 하나의 변수에 대입하는 것 가능

const person1Married = person1['married'];  // # 2번 방법을 이용한 접근 방법

console.log(person1Age, person1Married);
```

- 프로퍼티를 추가
이 것도 2 가지 방법이 있습니다.

```js
const person1 = {
  name : '김일',           // css 할 때는 ; 썻는데 얘는 나열할 때 , 씁니다.
  age : 20,
  married : false,
};

person1.job = '프로그래머';    // # 1 방법
person1['bloodtype'] = 'B';  // # 2 방법

console.log(person1['job'], person1.bloodtype);
```

- 기존 프로퍼티 수정하기
```js
const person1 = {
  name : '김일',           // css 할 때는 ; 썻는데 얘는 나열할 때 , 씁니다.
  age : 20,
  married : false,
};
person1.age++;
console.log(person1)
```

- const로 person1을 지정했는데,  왜 수정이 될까요 ?
  - person1 자체는 const에 해당하지만, person1.age / person['age']는 const가 아닙니다. 그렇기 때문에 내부 property는 수정이 가능합니다.

  - 이걸 비유를 하자면
    - person1은 객체이면서, 하나의 집으로 규정된 상태. 따라서 집 자체를 바꾸는 것은 불가능하지만, 집의 내부에 있는 가구(값들)들은 집이 바뀌지 않는 한 수정이 불가능합니다.

집 자체를 바꾸는(객체의 property를 다 갈아버리는) 에시
```js
const person1 = {
  name : '김일',        
  age : 20,
  married : false,  // 이까지 썼을 때 맨 뒤에 ',' 찍어두는게 개발자들 사이의 매너라고 한다.
}

person1.job = '프로그래머';
person1['bloodtype'] = 'B';

person1 = {};           // 오류 발생 -> 멀쩡하게 있는 property를 다 날렸기 때문에 const를 수정한 것으로 간주함.
console.log(person1);
```

### 배열(Array)
- 배열도 여러 개의 데이터를 저장하기는 하는데, property의 형태가 아니라 element로만 저장하는 형태. 
- Java와는 달리 서로 다른 자료형들끼리도 하나의 묶음에 들어갈 수 있습니다.
- JS상에서는 배열 역시 근본적으로는 '객체의 한 종류'

```js
const person1 = {
  name : '김일',        
  age : 20,
  married : false,  
}
person1.job = '프로그래머';
person1['bloodtype'] = 'B';
const myArray1 = [true, 3.14, 'Hello', person1];
console.log(myArray1, myArray1.length);
```

- 배열의 요소에 접근하기
```js
const person1 = {
  name : '김일',        
  age : 20,
  married : false,  
}
person1.job = '프로그래머';
person1['bloodtype'] = 'B';
const myArray1 = [true, 3.14, 'Hello', person1];
console.log(
  myArray1[0],
  myArray1[1],
  myArray1[2],
  myArray1[3],
);
```
- myArray1.0 으로는 불가능할까요?
  - 변수명은 숫자로 시작할 수 없기 때문에 불가능하다. -> Java를 배운 우리는 [indexNumber]로 찾아간다.

- 배열의 element에 접근한 후에 그 값을 바꾸는 방법
```js
myArray1[0] = false;      // 이게 바꾼 것
```

- element 추가 및 삭제
```js
const array2 = ['안', '녕', '하', 3, false, 'not good today'];

// 요소 추가를 할 때는 Java와 다릅니다 -> Java는 배열 크기가 고정돼있어서 추가 불가능했죠
// 근데 list에서는 가능했었습니다, 그 부분을 생각해야됨.

array2.push(true);
array2[3] *= 100;
array2[5] += '🥦';
console.log(array2);

// 삭제 부분 설명
const popped1 = array2.pop(); 
console.log(array2, popped1);
```

- 배열명.pop(); 은 배열의 '맨 마지막 element를 반환'하고, '배열 상에서는 삭제' 합니다.

- 객체와 배열의 중첩 사용

```js
const person2 = {
  name: '김이',
  age : 22,
  languages: ['Korean', 'English', 'Japanese'],
  education : {
    school : '한국대',
    majors: ['컴퓨터공학', '영어교육'],
    graduated: true,
  },
};
console.log(person2);

// Japanese를 출력
console.log(person2.languages[2]);

// 컴퓨터공학을 출력
console.log(person2.education.majors[0]);
```

# 회고

1. 기술 불로그 -> .md파일
2. 프로그래머스 / 백준 -> 마찬가지로 기술불로그에 들어갈 소재가 됩니다.
3. 그렇다면 이제 기술 불로그에 올리는 것까지(단순히 .md를 정리하는 것이 아니라)
4. 기술불로그에 마지막 종갈이 전까지 몇 개 정도 올릴까
5. 정보처리기사 실기 -> 너무 어려웠다고 합니다 / 2회차가 쉬워집니다.
6. md 파일 정리하세요 -> 블로그에 올릴 수 있도록 가공하세요 -> 프로그래머스
7. 네이버블로그 / 티스토리 / velog <- 개발자 블로그
