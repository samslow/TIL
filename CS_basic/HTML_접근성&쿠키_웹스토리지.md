# 웹 표준과 시멘틱 웹 그리고 HTML

Date Created: Apr 28, 2020 8:48 PM

# 웹 표준

- 웹에서 사용되는 표준 기술이나 규칙
- W3C 권고안
    - png 사용, alt속성 사용, em 사용

# 시멘틱 웹

- 시멘틱 태그는 브라우저와 개발자에게 element의 의미를 명확히 전달 해 주기 때문에 중요하다.
    - `div, span` 은 맘대로 바꿀 수 있어 의미가 명확하지 않기 때문에 Non-semantic 태그이다.
- 시맨틱 마크업이란 의미를 잘 전달하도록 웹을 작성하는 것을 말한다.

# 크로스 브라우징

- 웹 표준에 따라 개발하고, 어떤 환경에서도 이상없이 작동하는 것
- 여러 브라우저에서 동일한 사용자 경험을 주기 위한 개념

# doctype의 의미

- HTML이 어떤 버전으로 작성되었는지 미리 선언하여 브라우저가 내용을 올바로 표시 할 수 있도록 해주는 것
- `<!DOCTYPE>` 으로 선언하고, 이게 없을때는 quirks mode로 동작하여 크로스 브라우징 이슈가 발생한다.
    - `<!DOCTYPE html>` 로 사용하면 HTML 5를 사용한다고 명시하는 것
    - quirks mode로 동작시 이전 세대 브라우저에 맞는 비표준적인 CSS를 적용한다.

# 쿠키와 웹스토리지

- 쿠키: 클라이언트에 대한 정보를 이용자의 PC에 보관하기 위해 서버가 전송하는 정보

## Web Storage

- key-value 구조
- 쿠키와 달리 서버에서 클라이언트에 대한 정보를 저장하지 않는다는 차이점

### LocalStorage

- Web Storage의 종류 중 하나
- Client의 정보를 반영구적으로 저장함

### SessionStorage

- Web Storage의 종류 중 하나
- Client의 정보를 세션이 끝나면 삭제함

## Cookie vs LocalStorage vs SessionStorage

- cookie 장점 : 어지간한 브라우져에는 지원이 다됨
- cookie 단점 : api가 한번 더 호출되므로 서버에 부담증가/ 쿠키자체의 용량이 적음

---

- LocalStorage 장점 : 서버에 불필요하게 데이터 저장안함/ 용량이 큼
- LocalStorage 단점 : HTML4만 지원되는 브라우져라면 지원이 안됨...
- SessionStorage의 장단점은 LocalStorage와 동일하다 LocalStorage와 단지 기능차이일뿐이다.