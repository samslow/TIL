# JS Promise 장단점

Date Created: May 04, 2020 12:14 AM
tag: CS기초

- 순차적이지 않은 비동기 함수의 실행 순서를 제어하는 Promise

# Promise의 장·단점

## 장점

- callback hell에서 벗어 날 수 있음
    - .then()의 return은 다음 .then()의 매개변수로 사용되므로 가독성 👆
- .then() 을 이용하여 가독성 좋은 연속적인 비동기 코드를 작성 가능
- Promise.all()을 통해 병렬 비동기 코드 작성 가능
    - 매개변수로 던져진 함수들이 모두 완료되면 return
- callback 함수를 제 때 실행하지 못하거나 변수 전달 실패 없음

## 단점

- ES5 이전에서는 polyfill을 통해 로드해야 함