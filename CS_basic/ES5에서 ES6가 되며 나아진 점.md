# ES5에서 ES6가 되며 나아진 점

- 내가 헷갈리는 것 위주로 정리하자

### 템플릿 리터럴

- 백틱을 사용하여 특수문자로 변수를 감쌀 필요가 없어졌다.

```jsx
const name = "서현석
console.log(`나는 ${name}입니다.`)
```

### 화살표 함수

- ES5에서는 3가지 방법으로 함수 선언
    - 함수 선언식

        ```jsx
        function str(a1,a2){
        	console.log(a1,a2)
        }
        ```

    - 생성자 함수

        ```jsx
        const str = new Function(a1, a2, console.log('h'))
        ```

    - 함수 리터럴( 익명 함수로 사용 )

        ```jsx
        const str = function(a1, a2){
        	conosole.log(a1, a2)
        }
        ```

- ES6에서는 화살표 함수로 함수 리터럴을 간단하게 할 수 있음.(단, this의 의미에 유념)

    ```jsx
    const str = (a1, a2) => {
    	console.log(a1, a2)
    }
    ```

    ### this의 다른 동작

    1. 메소드 콜

        ```jsx
        var obj = {
          value: 10;
          show: function () {
            console.log (this.value); // 10
          }
        }
        obj.show();
        ```

    2. 함수 콜

        ```jsx
        value = 1;
        function func() {
          var value = 2;
          console.log(this.value); // 1
        }
        func();
        ```

    3. 생성자 함수 콜

        ```jsx
        function Obj(value) {
          this.value = value;
        }
        var obj = new Obj(0);
        console.log(obj.value); // 0
        ```

        - this는 인스턴스를 가르킴
    4. apply, call, bind

        ```jsx
        var obj = {
          value: 1,
          show: function() {
            console.log(this.value);
          }
        };
        var newObj = {
          value: 5
        };
        obj.show(); //1
        obj.show.call(newObj); // 5;
        obj.show.apply(newObj); // 5;
        ```

        - call, apply로 첫번째 arg를 this를 바인딩 할 수 있다.
            
            - call은 순서대로 받고 apply는 배열로 받음.
    - bind는 this가 arg로 바인딩된 함수를 생성
    
            ```jsx
            var newFunc = obj.show.bind(newObj);
            newFunc(); // 5
        ```
    
    5. 화살표 함수 
        - 함수가 선언된 스코프에 자동으로 바인딩.
    - 함수 선언식으로 호출하면 그 함수 자체에 바인딩.
    
        ```jsx
        var obj = {
      value: 10,
    
          // 메소드 호출
          show: function () {
        console.log(this.value); // 10
    
            // 함수 호출
            function show_01 () {
              console.log(this.value); // undefined
            }
        show_01();
    
            // 화살표 함수
            const show_02 = () => {
              console.log(this.value); // 10
            }
            show_02();
          }
        }
        obj.show();
        ```

### 클래스

- 선언을 prototype으로 했으나, ES6 에선 class 키워드로 할 수 있음
- 클래스 상속을 extends를 써서 super()로 할 수 있음