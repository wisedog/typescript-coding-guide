# TypeScript Coding Guide

## 개요

본 문서는 TypeScript와 TypeScript의 뿌리인 JavaScript에 대한 코딩 가이드라인에 대해 정리한 문서입니다. TypeScript의 기능만으로는 절대 하나의 실행 가능한 프로그램을 만들 수 없기에, TypeScript 뿐만 아니라 JavaScript의 코딩 가이드라인로 같이 담았습니다.

하나의 동작 가능한 프로그램을 위해 필요한 가장 작은 단위인 식별자, 타입부터 시작하여 표현식, 문, 함수 순으로 가이드라인을 작성했습니다.

## 다루는 주제

1. 식별자(Identifier)
2. 타입(Types)
3. 선언과 정의(Declaration and Definition)
4. 클래스(Class)
5. 표현식(Expression)
6. 문(Statement)
7. 함수(Functions)
8. 에러 처리(Error Handling)
9. 표준 내장 객체 및 함수(Standard Built-in Objects/Functions)
10. 주석(Comment)
11. 소스코드(Source Code)
12. 기타(Misc)

## 구성

- 각 주제 별로 ID가 있으며 각 주제에는 여러 개의 부주제가 있습니다.
- 규칙 이름은 `Rule-{주제 ID}-{부주제 Sequence}-{Sequence}`으로 명명합니다.
- 각 규칙은 `필수`,`권장` 그리고 `참고`로 나눠집니다.
- `필수`는 지키는 걸 추천드리지만, 절대적이진 않습니다. 각종 예외를 둘 수도 있고, 프로젝트 별로 적용하지 않을 수도 있습니다.
- `권장`은 가능하면 지키되, `필수`보다는 강제로 적용하지 않아도 됩니다.
- `참고`는 알아두면 좋은 항목입니다.

## 토론/기여 방법

PR을 올려주시거나 `Discussions` 메뉴을 통해서 수정, 추가 규칙 제보 등이 가능합니다.

### 용어

- 브랜드 이름은 번역하지 않습니다.

```
자바스크립트(x), JavaScript(O)
타입스크립트(x), TypeScript(O)
```

- 용어는 [MDN 용어 가이드](https://github.com/mdn/translated-content/blob/main/docs/ko/guides/glossary-guide.md)에 따릅니다.

## 전체 규칙 목록

1. 식별자(Identifier)

- ID-1-1(권장): 식별자는 영어 알파벳, 숫자, 언더바 만을 사용해야 합니다.
- ID-1-2(필수): 모든 식별자는 카멜 케이스, 파스칼 케이스를 따릅니다
- ID-2-1(권장): 글로벌 상수는 대문자와 밑줄(언더바)로 이루어져야 합니다.
- ID-2-2(권장): `Array<T>`와 같은 타입 매개변수는 대문자 영문 알파벳 한 글자 혹은 Pascal Case를 사용하세요.
- ID-2-3(권장): 전위(Prefix) 언더바, 후위(Suffix) 언더바는 사용하지 말아야 합니다.
- ID-2-4(권장): 식별자에 의미를 충분히 담아야 합니다.

2. 타입(Types)

- TP-1-1(필수): 원시 타입(Primitive Type)은 래퍼(Wrapper) 객체를 사용하지 마세요.
- TP-1-2(필수): `Object`타입과 `Object` 생성자를 사용하지 마세요.
- TP-2-1(필수): `undefined`과 `null`을 구분해서 사용하세요.
- TP-2-2(필수): 타입 별칭에 `null`이나 `undefined`을 포함하지 마세요.
- TP-2-3(필수): `| undefined` 대신 `?`을 사용하세요
- TP-6-1(권장): `string`, `boolean`, `number`, `new` 표현식으로 초기화된 변수나 매개변수에 대한 타입 명시는 생략합니다.
- TP-6-2(필수): 반환 타입을 명시하세요

3. 선언과 정의(Declaration and Definition)

- DD-1-1(필수): `var` 대신 `const` 와 `let`을 사용하세요
- DD-1-2(필수): 변수가 다시 할당되지 않는다면 `const` 를 사용하세요.
- DD-1-3(필수): 지역 변수 선언 시 한 번에 하나의 변수 만을 선언해야 합니다

4. 클래스(Class)

- CL-1-1(필수): `readonly` 를 활용하세요
- CL-1-2(권장): `public` 접근 제어자에 일관성이 있어야 합니다.

5. 표현식(Expression)

- EX-1-1(권장): 2중 이상의 조건 표현식(Conditional Expression)은 사용하지 마세요.
- EX-1-2(필수): 부동 소수점의 값을 직접 비교하지 마세요.
- EX-1-3(권장): 단항 증가(unary plus, +) 연산자를 조심히 사용하세요
- EX-1-4(필수): `new` 연산자로 객체를 생성하세요.
- EX-1-5(필수): 전개 연산자 사용 시 피연산자가 객체 리터럴 혹은 순회 가능한 객체가 와야합니다.
- EX-1-6(필수): 전개 연산자 사용 시 값 덮어쓰기를 주의하세요.
- EX-1-7(필수): 전개 연산자 사용 시 같은 타입에 사용하세요
- EX-1-8(필수): 다차원 배열을 전개 연산자의 피연산자로 사용하지 마세요

6. 문(Statement)

- ST-1-1(필수): 복합문(Compound Statements)의 시작과 끝은 중괄호({})여야 합니다.
- ST-2-1(필수): `switch`의 `default`를 명시하세요.
- ST-2-2(권장): 각 `case`절은 `break` 혹은 `return`이 있어야 합니다.
- ST-2-3(권장): `case`가 3개 미만이면 `if...else`를 고려하세요
- ST-2-4(참고): `switch(true)` 패턴을 용도에 맞게 사용하세요
- ST-3-1(필수): `for...in` 사용 시, 명시적으로 필터링을 하세요.
- ST-3-2(필수): 배열을 순회 시 `for...in`을 사용하지 마세요.
- ST-3-3(필수): `for` 문에서 숫자 증감을 소수점으로 하지 마세요.
- ST-3-4(필수): for 문에서 반복 카운터로 사용하는 숫자 변수를 내부에서 변화시키지 마세요
- ST-3-5(권장): 배열을 순회할 목적이면 for 문 대신 `for...of`, `Array.prototype.forEach()`를 사용하십시오.
- ST-4-1(권장): 3개 이상의 조건은 지양하세요
- ST-4-2(권장): 조건에 부정 연산자, 부정적 의미를 담은 식별자는 최소한으로 사용하세요.
- ST-4-3(권장): `else if`가 3개 이상이면 `switch` 사용을 고려하세요

7. 함수(Functions)

- FC-1-1(권장): 매개 변수가 3개 이상인 함수는 구조적 타입으로 매개 변수를 줄여보세요.
- FC-1-2(권장): 매개 변수가 객체인 경우 `Readonly` 유틸리티 타입을 사용하세요

8. 에러 처리(Error Handling)

- EH-1-1(권장): `catch`절은 비워두지 마세요.
- EH-1-2(필수): 예외 값은 Error 만 사용하세요.

9. 표준 내장 객체 및 함수(Standard Built-in Objects/Functions)

- SD-2-1(필수): `Array.prototype.map()`은 호출한 `Array`의 요소의 값 만 변경시켜야 합니다.
- SD-2-2(필수): `Array.prototype.map()`의 반환 값을 반드시 사용하세요
- SD-2-3(필수): `Array` 생성자를 사용하지 마세요
- SD-2-4(필수): `Array.prototype.forEach()` 내에서 값을 반환하지 마세요.
- SD-2-5(필수): `Array.prototype.forEach()`에서 `await` 를 사용하지 마세요
- SD-2-6(필수): `Array` 순회 가능한 메서드의 콜백 함수 내에서 대상 Array 값을 수정하지 마세요
- SD-2-7(권장): `Array` 메서드 사용시 가능하면 불변을 유지하는 메서드를 사용하세요.
- SD-2-8(필수): 전역 함수보다는 `Number` 전역 객체의 함수를 사용하세요.
- SD-2-9(필수): `String` 전역 객체의 `trimLeft()`, `trimRight()`보다 `trimStart()`, `trimEnd()`를 사용하세요.
- SD-2-10(권장): 해시맵이 필요할 때 `Object`대신 `Record` 혹은 `Map`을 사용하세요.
- SD-2-11(권장): Unix Time Epoch를 구할때 `Date.now()`를 사용하세요.
- SD-3-1(필수): `eval()`을 사용하지 마세요
- SD-3-2(권장): 객체 깊은 복사가 필요할 때 `structuredClone()`을 사용하세요

10. 주석(Comment)

- CM-1-1(필수): 클래스 멤버, 클래스 메서드, 함수, 속성 선언 등 에는 TSDoc 형태의 주석을 사용하세요.
- CM-1-2(필수): 한 줄 주석은 `//`을 사용하세요
- CM-1-3(권장): 주석은 데코레이터 위에 다세요.
- CM-1-4(권장): 불필요한 블록 태그는 사용하지 마세요.
- CM-1-5(참고): 권장 블록 태그는 적극적으로 사용하세요.
- CM-1-6(참고): JSDoc(TSDoc)은 마크다운 형식을 따릅니다.

11. 소스코드(Source Code)

- SC-1-1(필수): 코드 스타일은 일관성이 있어야 합니다.
- SC-1-2(필수): `namespace`를 사용하지 마세요.
- SC-3-1(필수): `default export`를 사용하지 마세요.

12. 기타(Misc)

- EV-2-1(필수): 소스코드는 `UTF-8`인코딩으로 저장되어야 합니다.
