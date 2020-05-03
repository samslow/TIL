# JS Closure

Date Created: May 04, 2020 12:22 AM
tag: CS기초

- 클로져는 함수와 그 함수가 선언됐을 때의 어휘적인 환경(Lexical Environment)의 조합이다.
- 즉, 내부함수를 포함하고 있는 외부 함수가 있고, 내부함수가 더 오래 유지되는 경우라고 할 지라도 외부함수의 지역변수에 접근 할 수 있도록 기억하는 것을 말한다.
- 함수가 호출되면 자신의 실행 컨텍스트가 시스템 실행 컨텍스트에 스택으로 쌓이고 변수 객체와 스코프 체인, this에 바인딩할 객체가 결정되는 성질을 이용한 것이다.
- 단, 주의할 점은 외부함수가 이미 반환되었어도 그 안의 변수는 복사본이 아니라 실제 변수로 존재한다는 것을 기억해야한다.
    - 즉, 내부 함수에서 값을 변경하면 해당 변수는 외부함수가 반환되었어도 변경된다.
    - 외부 함수는 이미 반환됐고 그때의 상태를 기억하는 것이라고 생각해 버리면 버그로 이어지기 쉽다.

```jsx
function counter() {
    var count = 0;
    
    function add() {
        count++;
        console.log(count);
    }
    
    return add;
}

const increaseCounter = counter()
const ic = couner()
increaseCounter() // 1
ic() // 1

```

- 위의 예시에서 보면, counter()는 이미 반환되었지만, count는 계속해서 상태를 유지하기 때문에 counter() 인스턴스마다 counter는 0에서 시작하고, 값이 변경된다.