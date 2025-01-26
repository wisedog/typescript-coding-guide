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
- 각 규칙은 `필수`와 `권장`으로 나눠집니다.
- `필수`는 지키는 걸 추천드리지만, 절대적이진 않습니다. 각종 예외를 둘 수도 있고, 프로젝트 별로 적용하지 않을 수도 있습니다.
- `권장`은 가능하면 지키되, `필수`보다는 강제로 적용하지 않아도 됩니다.

## 토론/기여 방법

PR을 올려주시거나 `Discussions` 메뉴을 통해서 수정, 추가 규칙 제보 등이 가능합니다.

### 용어

- 브랜드 이름은 번역하지 않습니다.

```
자바스크립트(x), JavaScript(O)
타입스크립트(x), TypeScript(O)
```

- 용어는 [MDN 용어 가이드](https://github.com/mdn/translated-content/blob/main/docs/ko/guides/glossary-guide.md)에 따릅니다.
