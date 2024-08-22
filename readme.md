# you don't know JS yet 스터디 기록물

## Part 1

1. 자바스크립트

   1. 자바스크립트는 넷스케이프에 재직중이던 브랜던 아이크가 모카라는 암호명으로 제작했으며 외부에 공개할 때 '자바스크립트' 로 명명했다.
   2. 자바개발자들의 입맛에 맞게 만들었고, 개발자들에게 어필하기 위해 마케팅 목적으로 '자바스크립트'라고 명명했으며 이는 자바와는 별개의 언어이다.
   3. ECMA 표준 기구에 의해 공식화된 명칭으로는 ECMAScript 라고 불린다. 2016년 이후부터는 개정 연도를 붙여서 표기한다.

      > **ECMAScript 1 (ES1)** - 1997년 6월 - 최초의 ECMAScript 표준.  
      > **ECMAScript 2 (ES2)** - 1998년 6월 - 문서화 및 편집상의 변경만 포함한 소규모 업데이트.  
      > ECMAScript 3 (ES3) - 1999년 12월 - 레귤러 익스프레션, 새로운 제어문, try/catch 예외 처리, 더 엄격한 오류 처리 등을 포함.  
      > ECMAScript 4 (ES4) - 취소됨 - 이 버전은 제안되었으나, 지나치게 복잡하다는 이유로 표준화되지 않았고 취소되었습니다.  
      > ECMAScript 5 (ES5) - 2009년 12월 - strict mode, JSON, Array 메서드 (forEach, map, filter, reduce, some, every 등), Object 메서드 (Object.keys, Object.create 등) 포함.  
      > ECMAScript 5.1 (ES5.1) - 2011년 6월 - ECMAScript 5의 수정판. 주로 문서화 수정이 포함되었으며, 이 버전은 ISO/IEC 16262:2011으로 표준화됨.  
      > ECMAScript 6 (ES6, ECMAScript 2015) - 2015년 6월 - 모듈, 클래스, 화살표 함수, let, const, 템플릿 리터럴, Promise, 제너레이터, for...of, 심볼, 맵과 셋 등의 큰 변화와 새로운 기능들 포함.  
      > ECMAScript 7 (ES7, ECMAScript 2016) - 2016년 6월 - 두 가지 주요 기능: Array.prototype.includes, 지수 연산자(\*\*).  
      > ECMAScript 8 (ES8, ECMAScript 2017) - 2017년 6월 - async/await, Object.values, Object.entries, String.prototype.padStart, String.prototype.padEnd, 트레일링 쉼표(함수 매개변수) 포함.  
      > ECMAScript 9 (ES9, ECMAScript 2018) - 2018년 6월 - Rest/Spread Properties, 비동기 이터레이션(for await...of), 정규 표현식 개선, Promise.prototype.finally 포함.  
      > ECMAScript 10 (ES10, ECMAScript 2019) - 2019년 6월 - Array.prototype.flat, Array.prototype.flatMap, Object.fromEntries, String.prototype.trimStart, String.prototype.trimEnd, Optional Catch Binding, 심볼 설명(Symbol Description) 포함.  
      > ECMAScript 11 (ES11, ECMAScript 2020) - 2020년 6월 - 널 병합 연산자(??), 선택적 체이닝(?.), 글로벌 This, 동적 import, BigInt, Promise.allSettled, 모듈의 네임스페이스 export, import.meta 포함.  
      > ECMAScript 12 (ES12, ECMAScript 2021) - 2021년 6월 - String.prototype.replaceAll, 논리 할당 연산자(&&=, ||=, ??=), WeakRefs, FinalizationRegistry, Promise.any 포함.  
      > ECMAScript 13 (ES13, ECMAScript 2022) - 2022년 6월 - Array 및 TypedArray의 at(), Object.hasOwn, Error 원인 속성, import.meta.resolve 포함.  
      > ECMAScript 14 (ES14, ECMAScript 2023) - 2023년 6월 - Array.findLast(), Array.findLastIndex(), Hashbang(#!), Symbol.prototype.description, Array.fromAsync, 버퍼링된 문자셋과 정규식 개선 포함.

   4. 자바스크립트의 명세는 TC39 라는 자바스크립트를 관리하는 기술 운영 위원회에서 관리한다.
   5. 제안서 작성은 누구에게나 열려있으며, 해당 제안이 명세에 추가되려면 TC39 위원의 지원을 받아야한다
   6. 간혹 새로운 동작이 추가되거나 기존 작동 방식을 변경하는 등 명세서가 개정이 될 수 있다. 기존에 자바스크립트의 엔진을 만드는 곳들은 오랜시간 기능을 구현하다보니 오류에 대해 처리하기 위해 엣지케이스를 다루는 기능을 **자체적**으로 추가했는데 이런 상황에서 명세서 개정안이 반영됐을 때, 기존에 문제가 없던 부분에서 문제가 나올 경우 **자사 엔진에 반영하지 않겠다고 강짜부림** 그렇게 불일치가 발생하게 되면 TC39는 종종 기존 결정을 철회하고 명세서를 웹에 맞추기도 함.
   7. 자바스크립트에서 사용되지만 자바스크립트가 아닌 메서드가 있다.
      EX - alret, console.log, console.info 등등
   8. 자바스크립트는 다중 패러다임 언어로써 절차적, 객체지향, 함수형 스타일의 코드를 모두 사용할 수 있다.
   9. 자바스크립트는 하위호환성을 보장한다. 따라서 브라우저의 버전이 업데이트 되더라도 그 이전에 작성된 코드는 무조건 동작을 보장받을 수 있다. 단, 상위호환성은 보장하지 않는다.
      > 하위호환성 ? 예를 들어 약 10년전에 작성한 JS 코드가 있다면 현재(2024년)의 브라우저 또는 엔진에서 해당 코드의 동작이 보장된다는 개념.
      > 상위호환성 ? 하위호환성과 반대되는 개념으로 최신의 문법(또는 메소드)인 경우 구형 브라우저에서는 의도한 동작이 실행되지 않는다는 개념.

   **문제** 하위호환성을 알아볼수 있는 코드들을 찾아보면 어떨까요? 또는 상위호환성 코드를 찾아보는것도
   좋을 것 같습니다.

   10. 최신의 문법을 사용하여 개발 할 때는 구형 브라우저에서도 동일한 동작이 이뤄질 수 있도록 **바벨**과 같은 트랜스파일러의 도움을 받을 수 있다. 트랜스파일러는 최신 형태의 문법을 이전 형태의 문법으로 변환하여 소스로 반환해준다.

   11. 최신의 기능을 구형 브라우저 또는 엔진에서 사용할 수 있게 하는데 필요한 코드를 폴리필(polyfill) 또는 심(shim)이라고 함
