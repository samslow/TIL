# JS Event loop

Date Created: May 04, 2020 1:11 AM
tag: CS기초

# Callstack

- JS는 싱글 스레드 방식이기 때문에 "Run to Completion"으로 함수가 한번 실행되면 이 함수가 끝날 때 까지 다른 함수는 실행 될 수 없다는 의미이다.
- JS는 단 하나의 호출 스택(callstack)을 사용한다.
- callstack은 원시타입 값과 함수 호출의 실행 컨텍스트를 저장하는 곳이다.

# Task Queue(Event Queue)

- 처리해야 할 Task들이 대기하는 Queue이다.
- callstack이 비워졌을 때 대기하던 순서대로 callstack에서 수행된다.

```jsx
function test1(){
	console.log("test1");
	test2();
}

function test2(){
	let timer = setTimeout(function() {
		console.log("test2");
	, 0);
	test3();
}

function test3(){
	console.log("test3");
}

test1(); // ?
```

- 먼저 test1이 callstack에 push되고 이어서 test2가 푸시되며 setTimeout()이 callstack에 들어오지만 핸들러(익명함수)이기 때문에 **바로 실행되지 않고** event queue로 보내진다.
- 이어서 test3가 callstack에서 실행을 마친 후 pop되고, test2와 test1까지 모두 pop되면 event queue에 처음에 있던 setTimeout이 callstack에 들어와 실행된다.
- 즉, 이벤트에 걸려있는 핸들러는 절대 먼저 실행 될 수 없다.

# 결론

- 이러한 callstack과 taskqueue의 상호작용이 JS의 event loop이다.
- stack과 queue를 활용한 간단한 자료구조로 구현되어 있다.

Event Loop는 callstack과 task Queue를 while로 반복적으로 확인하여 현재 수행중인 작업을 확인하여 적절히 loop를 돌린다. 

# Reference

- [https://asfirstalways.tistory.com/362](https://asfirstalways.tistory.com/362)