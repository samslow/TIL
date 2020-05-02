# mutable & immutable

Date Created: Apr 28, 2020 12:31 AM
tag: CS기초

# mutable & immutable

- 의도치 않은 객체 변경은 주로 '레퍼런스 참조한 다른 객체에서 객체 변경시' 발생하기 때문에 꼭 객체를 복사하여 사용하도록 한다.
- JS의 immutable Object
    - boolean
    - null
    - undefined
    - Number
    - String
    - Symbol(New in ES6)
- 원시타입 외 모든 값은 객체이자 mutable한 값이다.
- immutable 장점: 변경점을 찾기가 쉽고 디버깅이 쉬움

#