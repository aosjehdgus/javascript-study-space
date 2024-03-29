### 스코프(scope)란?

**식별자의 유효 범위를 뜻하며, 선언된 위치에 따라 유효 범위가 달라진다.** 전역에 선언된 변수는 전역 스코프를, 지역에 선언된 변수는 지역 스코프를 갖는다. 전역 변수는 어디에서든지 참조가 가능한 값이다.

반면, 지역 변수는 함수 몸체 내부를 말한다. 따라서 지역 변수는 자신의 지역 스코프와 그 하위 지역 스코프에서 유효하다.

### 블록 레벨 스코프

**자바스크립트에서 모든 코드 블록이 지역 스코프를 만들며 이를 블록 레벨 스코프라고 한다.** 코드 블록 내에서 선언된 변수는 코드 블록 내에서만 유효하며 코드 블록 외부에서는 참조할 수 없다.

### 함수 레벨 스코프

**var 키워드로 선언된 변수는 오로지 함수의 코드 블록만을 지역 스코프로 인정한다. 이를 함수 레벨 스코프라 한다.** 함수 내에서 선언된 변수는 함수 내에서만 유효하며 함수 외부에서는 참조할 수 없다. 즉, 함수 내부에서 선언한 변수는 지역 변수이며 함수 외부에서 선언한 변수는 모두 전역 변수이다.

아래의 예제를 살펴보자.

```jsx
    var a = 1;
     if(true){
        var a = 2;
    }

    console.log(a) // 2;

```

var 키워드를 이용해 a를 함수가 아닌 곳에서 선언했기 때문에 전역 변수로 취급한다. 기존에 있던 a 변수가 중복 선언되면서, 최하단의 console에서도 출력 값이 2로 바뀐 것을 확인할 수 있다.

그렇다면 아래의 예제의 경우는 어떻게 될까?

```jsx
    var a = 1;
     function test(){
        var a = 2;
    }

    console.log(a) // 1;

```

var 키워드를 중복 선언할 때 함수 안에서 선언하였기 때문에, 함수 외부에서는 참조할 수 없게 된다. 따라서 함수 스코프 바깥의 전역 변수인 var a의 값인 1이 출력되는 것을 알 수 있다.