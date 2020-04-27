# CSS 기초

Date Created: May 02, 2020 8:33 PM

# 개념 정리

- pseudo elements
    - element의 특정 부분을 스타일 넣는데 사용
    - ::first-letter, ::before
- pseudo class
    - element 상태 정의 위해 쓰임
    - a:hober, a:first-child
- image sprites
    - 이미지들을 하나의 이미지로 병합하여 서버요청시간과 응답 속도를 개선하는 방법
    - background position 을 조정하여 사용
- em vs rem
    - 둘 다 상대적인 크기를 정하는 데 사용하는 사이즈
    - em은 **상위 요소의** 몇 배로 할 것인지 정함
    - rem은 문서 **최상위 요소(html)** 크기의 몇 배크기로 할 것인지 정함

# 면접 질문

1. inline과 liline-block 차이점
    - inline: width, height, padding 등의 영향을 받지 않고 컨텐츠 크기대로 쭉쭉 늘어남
    - inline-block: width, height, 일렬 배치 등의 영향을 받아서 적용 됨
2. 컨텐츠를 보이지 않게 하는 기술에는 어떤것이 있을까요?
    - display: none
    - visibility: hidden (영역은 존재하나 보이지 않음)
    - position: absolute, overflow: hidden (스크린 리더로는 보임)
    - text-indent, z-index: 음수 (스크린 리더로는 보임)
3. Flash of Unstyled Content 설명 & 피하는 방법
    - StyleSheet가 로드 되기 전 raw content가 잠깐 번쩍 뜨는 현상
    - <head/> 에 css를 로드하거나 js로 모두 로드시 보여준다.
4. CSS 애니메이션과 JS 애니메이션의 차이점
    - Cross Browsing 면에서는 JS 만 사용하는것이 낫지만, CSS는 모든 동작을 CSS에서 관리할 수 있기 때문에 JS는 이벤트 감지로만 사용하는것이 유용하다.
    - CSS는 실행 로직 자체가 브라우저에 내장된 기능을 사용하기때문에 메모리 최적화가 되어있어 유리하다.
    - JS에서는 CSS, 동작 모두를 관리해야 하지만 CSS에서는 그 안에서 다 처리하기 때문에 용이하다.
    - 하지만 실제로 JS로 구동하는게 효율적일 수도 있다.