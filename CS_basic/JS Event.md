# JS Event 전달 방식

Date Created: May 04, 2020 12:52 AM
tag: CS기초

# 이벤트 버블링 Event Bubbling

- 바다 깊숙한곳에서 공기가 발생하면 부력에의해 공기방울이 수면까지 뽀글뽀글거리며 올라오는 것을 생각해보자.
- 이벤트 버블링은 특정 화면 요소에서 이벤트가 발생했을 때, 해당 이벤트가 트리의 상위 요소들로 전달되어가는 특성을 의미한다.

![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/7a75e2a5-95ad-4e26-9958-20d441460b6f/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200503%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200503T162759Z&X-Amz-Expires=86400&X-Amz-Signature=97eb45f07f011f153303dbb08ef9605acd133487db3315a3ae57e3565aa353ec&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

- 따라서 특정 이벤트가 발생하면 해당 요소로부터 body(혹은 더 상위) 까지 같은 이벤트를 전달하는 방식을 이벤트 버블링이라고 한다.

```jsx
<body>
	<div class="one">
		<div class="two">
			<div class="three">
			</div>
		</div>
	</div>
</body>
```

```jsx
var divs = document.querySelectorAll('div');
divs.forEach(function(div) {
	div.addEventListener('click', logEvent);
});

function logEvent(event) {
	console.log(event.currentTarget.className);
}

// three
// two
// one
```

# 이벤트 캡처 - Event Capture

- 이벤트 캡처는 이벤트 버블링과 반대로 진행되는 이벤트 전파 방식

![JS%20Event/Untitled%201.png](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/074d7d57-be3d-4afd-8770-983a39427fed/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200503%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200503T162956Z&X-Amz-Expires=86400&X-Amz-Signature=0e21fd8164eca6ff2d056aa694ef8f43f00ccd105136b72d155147d0da5a1695&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

```jsx
var divs = document.querySelectorAll('div');
divs.forEach(function(div) {
	div.addEventListener('click', logEvent, {
		capture: true // default 값은 false입니다.
	});
});

function logEvent(event) {
	console.log(event.currentTarget.className);
}
```

- 위와 같이 addEventListener의 2번째 옵션 매개변수에 capture: true(default is false)를 전달 해 주면 된다.

# 이벤트 전파를 막고 싶다면

```jsx
function logEvent(event){
	event.stopPropagation();
}
```

- 클릭 요소에만 이벤트를 발생시키고 이벤트 버블링이나 이벤트 캡처를 발생시키지 않는다.

# 이벤트 위임 - Event Delegation

- 하위 요소에 각각 이벤트를 붙이지 않고 상위 요소에서 하위 요소의 이벤트들을 제어하는 방식
- 리스트에서 새로운 목록이 생기면 매번 이벤트를 달아줘야할까? ⇒ 🙅‍♂️
- 개별 요소에 `addEventListener()` 를 달아주지 말고 상위 요소에 달아주면 된다.
    - <li /> 의 상위 요소인 <ul/> or <ol/>에 이벤트 리스너를 달아주면 된다.

# Reference

- [https://joshua1988.github.io/web-development/javascript/event-propagation-delegation/](https://joshua1988.github.io/web-development/javascript/event-propagation-delegation/)