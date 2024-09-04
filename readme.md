# you don't know JS yet 스터디 기록물

- [you don't know JS yet 스터디 기록물](#you-dont-know-js-yet-스터디-기록물)
  - [Part 1](#part-1)
    - [CHAPTER 1. 자바스크립트](#chapter-1-자바스크립트)
      - [1.2 자바스크립트의 유래](#12-자바스크립트의-유래)
      - [1.3 명세서](#13-명세서)
      - [1.3.1 JS를 지배하는 웹](#131-js를-지배하는-웹)
      - [1.3.2 JS지만 JS가 아닌 웹 전용 문법](#132-js지만-js가-아닌-웹-전용-문법)
      - [1.3.3 모든 코드가 JS는 아니다?](#133-모든-코드가-js는-아니다)
      - [1.4 JS의 다양성](#14-js의-다양성)
      - [1.5 하위 호환성과 상위 호환성](#15-하위-호환성과-상위-호환성)
      - [1.5.1 상위 호환성의 간극 줄이기](#151-상위-호환성의-간극-줄이기)
      - [1.6 인터프리터 이해](#16-인터프리터-이해)
      - [1.6.1 웹어셈블리](#161-웹어셈블리)
      - [1.7 엄격모드(stric mode)](#17-엄격모드stric-mode)
    - [CHAPTER 2. 자바스크립트 조망하기](#chapter-2-자바스크립트-조망하기)
      - [2.1 파일은 프로그램입니다](#21-파일은-프로그램입니다)
      - [2.2 값(value)](#22-값value)
      - [2.2.1 배열과 객체](#221-배열과-객체)
      - [2.2.2 값의 타입](#222-값의-타입)
      - [2.3 변수 선언과 사용](#23-변수-선언과-사용)
      - [2.4 함수](#24-함수)
      - [2.5 비교](#25-비교)
      - [2.5.1 같음에 대한 고찰](#251-같음에-대한-고찰)
      - [2.5.2 강제 변환](#252-강제-변환)
      - [2.6 코드 구조화 패턴](#26-코드-구조화-패턴)
      - [2.6.1 클래스](#261-클래스)
      - [2.6.2 모듈](#262-모듈)

## Part 1

### CHAPTER 1. 자바스크립트

#### 1.2 자바스크립트의 유래

- 자바스크립트는 넷스케이프에 재직중이던 브랜던 아이크가 모카라는 암호명으로 제작했으며 외부에 공개할 때 '자바스크립트' 로 명명했다.
- 자바개발자들의 입맛에 맞게 만들었고, 개발자들에게 어필하기 위해 마케팅 목적으로 '자바스크립트'라고 명명했으며 이는 자바와는 별개의 언어이다.

#### 1.3 명세서

- ECMA 표준 기구에 의해 공식화된 명칭으로는 ECMAScript 라고 불린다. 2016년 이후부터는 개정 연도를 붙여서 표기한다.

  > ## ECMAScript의 버전?
  >
  > <table>
  > <tr>
  > <th>이름</th>
  > <th>출판일</th>
  > <th>추가된 내용</th>
  > </tr>
  > <tr>
  > <td><span style="font-weight:700">ECMAScript 1 (ES1)</span></td>
  > <td>1997년 6월</td>
  > <td>최초의 ECMAScript 표준.</td>
  > </tr>
  > <tr>
  > <td><span style="font-weight:700">ECMAScript 2 (ES2)</span></td>
  > <td>1998년 6월</td>
  > <td>문서화 및 편집상의 변경만 포함한 소규모 업데이트.</td>
  > </tr>
  > <tr>
  > <td><span style="font-weight:700">ECMAScript 3 (ES3)</span></td>
  > <td>1999년 12월</td>
  > <td>레귤러 익스프레션(Regular Expression, 정규표현식), 새로운 제어문, try/catch 예외 처리, 더 엄격한 오류 처리 등을 포함.</td>
  > </tr>
  > <tr>
  > <td><span style="font-weight:700">ECMAScript 4 (ES4)</span></td>
  > <td>취소됨</td>
  > <td>이 버전은 제안되었으나, 지나치게 복잡하다는 이유로 표준화되지 않았고 취소되었습니다.</td>
  > </tr>
  > <tr>
  > <td><span style="font-weight:700">ECMAScript 5 (ES5)</span></td>
  > <td>2009년 12월</td>
  > <td>strict mode, JSON, Array 메서드 (forEach, map, filter, reduce, some, every 등), Object 메서드 (Object.keys,   Object.create 등) 포함.
  > </td>
  > </tr>
  > <tr>
  > <td><span style="font-weight:700">ECMAScript 5.1 (ES5.1)</span></td>
  > <td>2011년 6월</td>
  > <td>ECMAScript 5의 수정판. 주로 문서화 수정이 포함되었으며, 이 버전은 ISO/IEC 16262:2011으로 표준화됨.</td>
  > </tr>
  > <tr>
  > <td><span style="font-weight:700">ECMAScript 6 (ES6, ECMAScript 2015)</span></td>
  > <td>2015년 6월</td>
  > <td>모듈, 클래스, 화살표 함수, let, const, 템플릿 리터럴, Promise, 제너레이터, for...of, 심볼, 맵과 셋 등의 큰 변화와 새로운 기능들 포함.</td>
  > </tr>
  > <tr>
  > <td><span style="font-weight:700">ECMAScript 2016 (ES7)</span></td>
  > <td>2016년 6월</td>
  > <td>두 가지 주요 기능: Array.prototype.includes, 지수 연산자(**).</td>
  > </tr>
  > <tr>
  > <td><span style="font-weight:700">ECMAScript 2017 (ES8)</span></td>
  > <td>2017년 6월</td>
  > <td>async/await, Object.values, Object.entries, String.prototype.padStart, String.prototype.padEnd, 트레일링 쉼표(함수 매개변수) 포함.</td>
  > </tr>
  > <tr>
  > <td><span style="font-weight:700">ECMAScript 2018 (ES9)</span></td>
  > <td>2018년 6월</td>
  > <td>Rest/Spread Properties, 비동기 이터레이션(for await...of), 정규 표현식 개선, Promise.prototype.finally 포함.</td>
  > </tr>
  > <tr>
  > <td><span style="font-weight:700">ECMAScript 2019 (ES10)</span></td>
  > <td>2019년 6월</td>
  > <td>Array.prototype.flat, Array.prototype.flatMap, Object.fromEntries, String.prototype.trimStart, String.prototype.trimEnd, Optional Catch Binding, 심볼 설명(Symbol Description) 포함.</td>
  > </tr>
  > <tr>
  > <td><span style="font-weight:700">ECMAScript 2020 (ES11)</span></td>
  > <td>2020년 6월</td>
  > <td>널 병합 연산자(??), 선택적 체이닝(?.), 글로벌 This, 동적 import, BigInt, Promise.allSettled, 모듈의 네임스페이스 export, import.meta 포함.</td>
  > </tr>
  > <tr>
  > <td><span style="font-weight:700">ECMAScript 2021 (ES12)</span></td>
  > <td>2021년 6월</td>
  > <td>String.prototype.replaceAll, 논리 할당 연산자(&&=, ||=, ??=), WeakRefs, FinalizationRegistry, Promise.any 포함.</td>
  > </tr>
  > <tr>
  > <td><span style="font-weight:700">ECMAScript 2022 (ES13)</span></td>
  > <td>2022년 6월</td>
  > <td>Array 및 TypedArray의 at(), Object.hasOwn, Error 원인 속성, import.meta.resolve 포함.</td>
  > </tr>
  > <tr>
  > <td><span style="font-weight:700">ECMAScript 2023 (ES14)</span></td>
  > <td>2023년 6월</td>
  > <td>Array.findLast(), Array.findLastIndex(), Hashbang(#!), Symbol.prototype.description, Array.fromAsync, 버퍼링된 문자셋과 정규식 개선 포함.</td>
  > </tr>
  > <tr>
  > </tr>
  > </table>

  **출처 - chat gpt**

- 자바스크립트의 명세는 TC39 라는 자바스크립트를 관리하는 기술 운영 위원회에서 관리한다.
- 제안서 작성은 누구에게나 열려있으며, 해당 제안이 명세에 추가되려면 TC39 위원의 지원을 받아야한다

#### 1.3.1 JS를 지배하는 웹

- 간혹 새로운 동작이 추가되거나 기존 작동 방식을 변경하는 등 명세서가 개정이 될 수 있다. 기존에 자바스크립트의 엔진을 만드는 곳들은 오랜시간 기능을 구현하다보니 오류에 대해 처리하기 위해 엣지케이스를 다루는 기능을 **자체적**으로 추가했는데 이런 상황에서 명세서 개정안이 반영됐을 때, 기존에 문제가 없던 부분에서 문제가 나올 경우 **자사 엔진에 반영하지 않겠다고 강짜부림** 그렇게 불일치가 발생하게 되면 TC39는 종종 기존 결정을 철회하고 명세서를 웹에 맞추기도 함.

#### 1.3.2 JS지만 JS가 아닌 웹 전용 문법

- 자바스크립트에서 사용되지만 자바스크립트가 아닌 메서드가 있다. EX) alert, console.log, console.info 등

#### 1.3.3 모든 코드가 JS는 아니다?

- 콘솔에 입력한 코드는 JS 엔진이 .js 파일을 다루는 방식과 동일한 방식으로 처리되지는 않는다.
- 콘솔에 나타난 결과가 JS 문법을 **정확히** 지키더라도 결과를 신뢰하지 말고, 개발자 도구는 "JS에 우호적인" 별도의 환경임을 유념

#### 1.4 JS의 다양성

- 자바스크립트는 다중 패러다임 언어로써 절차적, 객체지향, 함수형 스타일의 코드를 모두 사용할 수 있다.

#### 1.5 하위 호환성과 상위 호환성

- 자바스크립트는 하위호환성을 보장한다. 따라서 브라우저의 버전이 업데이트 되더라도 그 이전에 작성된 코드는 무조건 동작을 보장받을 수 있다. 단, 상위호환성은 보장하지 않는다.

  > - 하위호환성 ? 예를 들어 약 10년전에 작성한 JS 코드가 있다면 현재(2024년)의 브라우저 또는 엔진에서 해당 코드의 동작이 보장된다는 개념.
  > - 상위호환성 ? 하위호환성과 반대되는 개념으로 최신의 문법(또는 메소드)인 경우 구형 브라우저에서는 의도한 동작이 실행되지 않는다는 개념.

  <span style="color: red; font-weight: 700">문제 ? </span> 하위호환성을 알아볼수 있는 코드들을 찾아보면 어떨까요? 또는 상위호환성 코드를 찾아보는것도 좋을 것 같습니다.

#### 1.5.1 상위 호환성의 간극 줄이기

- 최신의 문법을 사용하여 개발 할 때는 구형 브라우저에서도 동일한 동작이 이뤄질 수 있도록 **바벨**과 같은 트랜스파일러의 도움을 받을 수 있다. 트랜스파일러는 최신 형태의 문법을 이전 형태의 문법으로 변환하여 소스로 반환해준다.

- 최신의 기능을 구형 브라우저 또는 엔진에서 사용할 수 있게 하는데 필요한 코드를 폴리필(polyfill) 또는 심(shim)이라고 함

  > 폴리필이 필요할 때는 폴리필을 모아놓은 ES-Shim 과 괕은 공신력있는 폴리필을 사용하는게 좋다.
  > https://www.npmjs.com/org/es-shims //NPM에서 검색시 다양한게 나오는 듯?

- 바벨과 같은 트랜스파일러는 폴리필이 필요한 코드가 있는 경우 자동으로 폴리필을 추가하기도 함
- 해당 책의 저자의 경우 JS는 지속적인 진화가 이뤄질 것이고, 구 버전과의 간극은 절대 사라지지 않을 거기에 JS 기반 프로젝트에서는 트랜스파일이나 폴리필 사용이 표준으로 자리 잡아야 한다고 생각한다고 함

#### 1.6 인터프리터 이해

- **인터프리터 언어란 ?** 코드를 한 줄씩 읽어 내려가며 실행하는 프로그램. (출처 - 나무위키)

  - 종류 : Python, Javascript, SQL, Ruby 등

- **스크립트 언어란 ?** 응프로그래밍 언어의 한 종류로, 기존에 이미 존재하는 소프트웨어(애플리케이션)를 제어하기 위한 용도로 쓰이는 언어이다.
  일반적인 응용 소프트웨어는 컴파일러를 사용하는 언어에 의해 기계어로 번역된 채로 실행되기 때문에, 수정이 빈번하게 발생하면 수정 후 일일이 컴파일을 다시 해야 한다. 덩치가 큰 프로그램은 컴파일 시간도 몇 시간 단위로 잡아먹는 일이 많은데다, 일일이 컴파일을 다시 하는 것도 상당히 귀찮은 작업이다.  
  이 때문에 수정이 빈번하게 발생하는 부분은 소스코드를 한줄 한줄 읽어 바로바로 실행하는 인터프리터 방식이 상당히 유리하다. 스크립트 언어는 이런 부분에 사용하기 위해 나온 것으로, 응용 소프트웨어에서 스크립트 언어에 맞는 API를 제공, 응용 소프트웨어와 상호작용하면서 돌아가게 된다.  
  인터프리터 언어와 헷갈리는 사람이 있는데 인터프리터 언어는 인터프리터 방식을 사용하는 언어를 뜻하고 스크립트 언어는 앞서 말했듯이 이미 존재하는 소프트웨어를 제어하기 위한 용도로 쓰이는 언어이다. 단지 스크립트 언어 용도상 인터프리터 방식이 유용하기 때문에 스크립트 언어 대부분이 인터프리터 방식을 쓰는 인터프리터 언어일 뿐.

  - 종류 : Javascript, Typescript, Actionscript,AutoHotkey, JSP, PHP 등

- **컴파일 언어란 ?** 컴파일 언어(compiled language)는 코드가 실행되기 전 컴파일러를 거쳐서 기계어로 모두 변환되어 실행되는 프로그래밍 언어이다. (출처 - 위키백과)
  - 종류 : C, C++, C#, Java, Go 등등

컴파일 언어는 소스코드 파싱 -> 컴파일러에게 전달 -> 기계어로 변환되어 실행
되는 과정을 거치게 되는 특징을 가지고 있다.

JS로 만들어진 소스 코드도 실행 전 파싱을 거치기 때문에 컴파일 언어 라고 부를 수 있다.

초기의 자바스크립트는 인터프리터 언어였지만, 현대의 자바스크립트 엔진(구글의 V8, 모질라의 스파이더몽키)은 JIT(Just-In-Time) 컴파일 기술을 탑재하여 사용하기 때문에 코드 실행 전 필요한 부분을 즉시 컴파일하여 실행 속도를 높였다.

이에 따라 JS는 인터프리터 언어지만 컴파일 언어의 특성도 갖게 됨.

JS가 파싱된다는 근거로는 명세서에 중복된 매개변수명과 같이
정적으로 탐지가 가능한 오류를 초기 오류(entry error)라고 부르고 가능하면 프로그램 실행 전에 초기 오류를 찾아낼 수 있어야 한다고 언급되었는데, 이는 파싱이 없다면 사전에 탐지할 수 없는 오류이기 때문이다.

#### 1.6.1 웹어셈블리

- 도구 기반으로 만든 프로그램이 JS 엔진에서 좀 더 효율적으로 처리된다는 사실을 기반으로 웹어셈블리(WebAssembly, Wasm)라는 기술을 공개함  
  ※ 해당 내용은 크게 중요한 내용이 아닌 듯 하여 그냥 이 정도가 있다 정도만 짚고 넘어가면 될듯

#### 1.7 엄격모드(stric mode)

- stric mode를 바라보는 시점은 '할 수 없는 것에 제약을 두는 모드' 가 아니라 js엔진이 코드를 최적화 하고 효율적으로 실행할 수 있게 해주는 '안내 가이드 역할을 하는 모드'로 봐야한다.
- 엄격모드는 파일을 대상으로 처리 되기 때문에 파일에 전처리 구문이 'use Strict'가 있어야 활성화가 된다.
- 함수 단위로도 엄격모드를 설정할 수 있으며 함수의 시작 부분에 전처리 구문을 넣어주면 된다.
  ```javascript
  function useStrictMode() {
    //전처리 구문 상단에는 공백이나 주석만 적을 수 있음
    'use strict';
    // 전처리 구문 아래부턴 엄격 모드가 적용됨
  }
  ```
- 파일단위로 엄격모드를 사용한 경우 함수 단위에서 엄격모드는 적용이 불가 따라서 파일 단위 또는 함수 단위 중 선택하여 사용
- 함수 단위의 엄격 모드는 비 엄격 모드로 작성한 기존 코드를 <span style="color: red">**점진적으로 엄격 모드를 적용 해야 할 때만**</span> 사용하는게 좋다.
- 비 엄격 모드에서 작성 된 코드도 트랜스파일 처리 될 떄 엄격 모드를 준수하도록 변경된다(당혹스럽네???)
- 심지어 ES6의 모듈 형식으로 코드를 작성한 경우 ES6의 모듈은 기본이 엄격모드이다..;;

### CHAPTER 2. 자바스크립트 조망하기

- 가장 좋은 JS 학습 방법은 직접 코드를 작성하는 것 (인정..)

#### 2.1 파일은 프로그램입니다

- JS에서는 파일 각각이 별도의 프로그램이다.  
  이유 - JS는 파일을프로그램으로 취급하기 때문에 파일 하나에만 오류가 있어도 (파싱/컴파일 또는 실행단계) 다음 파일이 처리되지 않을 수 있다.
- 일반 유저의 경우 파일 단위로 실행하는 게 아닌 하나의 파일을 실행시켜 모든 기능을 동작하기 떄문에 단순히 하나의 프로그램만 만든 것이라고 생각할 수 있다. (이해됨, 항상 고객사는 단순히 생각하기 때문에 그냥 쉽게 얘기하는 듯?)

NOTE : 빌드 도구(웹팩 같은)가 하나의 파일로 만들고 배포하는데 이 경우 JS는 합쳐진 단일 파일을 전체 프로그램으로 취급

- 노트의 대한 주석에서 옮긴이가 현대 웹 개발에서 빌드 도구는 네트워크 효율성, 성능 최적화등의 이유로 여러 파일을 생성하는 경우가 더 많다고 얘기함 (개인적으로는 처음 듣는 방식이여서 놀램)  
   관련된 형태는 찾아보니 코드 스플리팅(Code Splitting) 이라고 함
  https://ko.legacy.reactjs.org/docs/code-splitting.html // 리액트 공식문서에서의 코드 스플리팅
  https://ui.toast.com/weekly-pick/ko_20200128 // Vue를 다루는 네이버의 토스트UI에서의 코드 스플리팅을 통해 사이트의 효율성을 높이는 방법  
   Ex - 코드 스플리팅을 활용한 대표적 사례 사이트  
   | 사이트 | 특징 | 이점 |
  |-----------|-------|------|
  | **YouTube** | - 복잡한 웹 애플리케이션<br>- 각 페이지마다 필요한 코드만 불러옴 | - 초기 로딩 시간 단축<br>- 사용자 경험 최적화 |
  | **Facebook** | - React 기반 웹 애플리케이션<br>- 기능 모듈을 별도 번들로 분리 | - 초기 로딩 시간 감소<br>- 특정 기능 사용 시 관련 스크립트만 로드 |
  | **Twitter** | - 실시간 소셜 미디어 플랫폼<br>- 코드 스플리팅과 지연 로딩 활용 | - 사용자 인터페이스 성능 최적화<br>- 특정 기능 사용 시 관련 코드만 로드 |
  | **Airbnb** | - 다양한 페이지와 기능 제공<br>- 사용자 상호작용에 따라 필요한 번들만 로드 | - 사이트 성능 최적화<br>- 빠른 페이지 로딩 |
  | **Amazon** | - 전자 상거래 플랫폼<br>- 제품 페이지와 장바구니 페이지가 별도 번들로 분리 | - 쇼핑 경험 최적화<br>- 빠른 로딩 시간 제공 |
  **출처 - 채찍피티**

- 독립적인 js 파일 여러개를 하나의 프로그램으로써 작동시키는 유일한 방법은 **전역 스코프(global scope)** 를 사용해 파일 간 상태를 공유하고 공통으로 사용하는 기능을 접근할 수 있도록 만드는 방법 뿐, 전역스코프의 네임스페이스에서 여러 js 파일이 조합되면 이 파일들은 런타임에서 하나의 애플리케이션으로 작동함

- 전역 스코프란? 브라우저의 window 객체 또는 Node.js의 global 객체와 같이 애플리케이션 전체에서 접근 가능한 범위를 의미  
  전역스코프는 전역 변수 사용은 관리하기 어려워질 수 있고, 다른 파일에서 동일한 이름을 사용하는 변수와 충돌이 발생할 수 있습니다. 따라서 유지보수성과 코드의 안정성을 해칠 수 있어 사용에 주의해야 한다고 함

> #### 전역스코프를 사용하여 독립적인 js파일을 하나의 애플리케이션처럼 작동시키는 예제
>
> file1.js
>
> ```javascript
> var MyApp = MyApp || {}; // 네임스페이스 정의
>
> MyApp.module1 = (function () {
>   function greet() {
>     console.log('Hello from Module 1');
>   }
>
>   return {
>     greet: greet,
>   };
> })();
> ```
>
> file2.js
>
> ```javascript
> var MyApp = MyApp || {}; // 네임스페이스 재사용
>
> MyApp.module2 = (function () {
>   function greet() {
>     console.log('Hello from Module 2');
>   }
>
>   return {
>     greet: greet,
>   };
> })();
> ```
>
> index.js
>
> ```javascript
> <script src="file1.js"></script>
> <script src="file2.js"></script>
> <script>
>    MyApp.module1.greet(); // "Hello from Module 1" 출력
>    MyApp.module2.greet(); // "Hello from Module 2" 출력
> </script>
> ```
>
> - MyApp이라는 전역 네임스페이스를 사용하여 두 파일에서 정의된 모듈들을 그룹화했습니다.
> - file1.js와 file2.js는 서로 독립적으로 작성되었지만, 같은 네임스페이스를 사용하여 전역 스코프에서 하나의 애플리케이션처럼 결합되었습니다.
> - index.html에서 각 모듈을 호출하여 실행할 수 있습니다.

- ES6 이후 모듈 포맷도 지원하는데 모듈 포맷도 파일 기반이다. JS는 각 모듈을 별도로 처리한다.
- 어쨌든 중요한건 js 파일 하나하나를 고유한 작은 프로그램이라고 생각해야 함

#### 2.2 값(value)

- 프로그램의 가장 기본적인 단위는 값(value), 값에는 데이터가 저장 됨
- 값으로 인해 상태를 유지할 수 있음
- 크게 원시 타입(primitive type, 프리미딥 타입ㅋㅋㅋ) 과 객체 타입(object type)으로 분류
- JS에서 리터럴을 사용해 프로그램에 값을 주입
- 문자열 범위를 정할 때는 큰따옴표, 작은따옴표, 백틱(`) 을 사용할 수 있음
- 단 백틱은 보간법을 위해 만들어졌으므로 백틱은 보간법을 사용할 때 쓰도록 하자!
- JS의 원시 타입 종류 - string, number, boolean, null, undefined, symbol, bigint
- 심볼은 일반적인 JS에서는 잘 사용하지 않는다. 보통 라이브러리나 프레임워크 같이 좀 더 저차원의 코드에서 사용한다.
- 원시타입의 값은 할당, 전달될 때 값이 복사되어 할당, 전달 된다.

#### 2.2.1 배열과 객체

- 배열은 인덱스가 있는 특수한 객체
- 배열은 객체에 포함
- 객체는 객체
- 함수도 객체 (자세한건 나중에?)
- 단 객체는 배열보다 좀 더 일반적인 데이터 타입
- 객체 접근방법은 온점('.') 말고도 []로 접근 가능

```javascript
ex)
 let me = {
  first : "k",
  last : "Paul",
  age : "비밀",
  "favorite color" : "blue"
 }

 // 온점(.) 접근방식
 me.age // 비밀

 // 대괄호[] 접근방식
 me["last"] // Paul
```

- 일반적인 온점 접근방식은 객체의 속성에 접근할 때 가장 일반적으로 사용
- 대괄호는 좀 특별해서 찾아봄  
  위 예제에서 key에 공백이 있는 형태가 있는데 저런 공백이 있는 형태이거나 또는 특수문자, 또는 속성 값이 동적일 때 접근용으로 사용함

```javascript
// 공백이 있는 key 인 경우
me['favorite color']; // blue

// 값이 동적인 경우 - 속성 이름이 변수로 지정되는 경우
let property = 'age';
me[property]; // 비밀
```

#### 2.2.2 값의 타입

- typeof 연산자를 통해 값의 타입을 확인할 수 있다
- null은 예상과 달리 object를 반환
- 문자열을숫자로 바꾸는 것처럼 값의 타입을 변경하는 것을 JS에서는 타입강제변환(coercion) 이라고 한다.

#### 2.3 변수 선언과 사용

- 변수 ? 값을 담는 상자라고 생각하면 됨, 식별자(identifier)라고도 불림
- 변수를 사용하려면 변수 선언이 선행
- 변수 선언 문법 - var, let, const
- let과 var의 선언 방식의 차이는 변수 접근 범위

```
* 변수 선언의 접근 범위
접근 범위 = 스코프
var = 함수 스코프
let = 블록 스코프
```

필자의 생각 ? var의 유효 범위에 대한 작동 방식은 혼란을 주다 보니 요즘에는 let과 const를 사용하라고 하지만, 지난친 제한이라고 생각한다고 함,

- const ? 선언 시 값을 할당해야 하고, 다른 값을 재할당할 수 없다.
- const 사용 시 주의 사항

```
const로 선언한 변수는 재할당이 불가능할 뿐 값을 바꿀수는 있다.
따라서 const를 사용해 객체를 정의하는건 좋지 않은 방식
const는 간단한 원싯값에 이름을 부여할 때 가장 적절

ex)

const myBirthday = 1231;
```

- var, let, const 외에도 특정 스코프 내에 변수와 같은 식별자를 선언하는 방법

```javascript
function hello(myName) {
  console.log(`${myName} 님, 안녕하세요:)`);
}

hello('카일'); //카일 님, 안녕하세요:)
```

그것은 함수로 정의하는 방법!

try..catch의 catch 구문에 전달하는 error도 블록 스코프이다.

#### 2.4 함수

※ 프로그래밍 언어에서 '함수' 의 의미?

- 함수형 프로그래밍 패러다임에서는 함수가 정확한 수학적 정의를 가지고 있으며 준수해야 할 엄격한 규칙의 집합

- js로 개발할 때 좀 더 포괄적인 개념인 '프로시저'를 프로그램에 녹여내기 위해 심사숙고하며 함수를 작성해야 함

> 나만 몰랐던 프로시저의 개념 - 이제 약간 이해가 됨
> 한번 이상 호출할 수 있고, 입력값이 있을 수 있으며 하나 이상의
> 출력 값을 반환하는 구문
>
> ```javascript
> function add(a, b) {
>   return a + b;
> }
>
> console.log(add(3, 4)); // 7
> ```
>
> 위 처럼 입력값이 있고 하나 이상의 값을 반환하면 프로시저로 볼 수 있다.
> 함수와 같은 개념으로 볼 수 있음

- 함수 사용방법

1.  함수 선언 (함수 선언문) 방식

```javascript
function awesomeFunction(collThings) {
  // ... 중략
  return amazingStuff;
}
```

- 위와 같은 방식을 함수 선언 또는 함수 선언문(function declaration)이라고 함
  ??? 함수 선언이란 이름은 이 함수가 다른 문의 표현식이 아니라 문 자체이기 떄문에 붙게됨?? 무슨 말인지 이해 안됨;;;

- 함수 선언으로 정의한 함수 awesomeFunction은 식별자 awesomeFunction과 실제 함수를 나타내는 값의 연관이 코드 실행 단계가 아닌 컴파일 단계에서 맺어짐

  2. 함수 표현식 방식

```javascript
let awesomeFunction = function (coolThings) {
  // ...
  return amazingStuff;
};
```

- 함수 표현식으로 선언된 함수는 식별자(위 예제에서는 awesomeFunction)가 코드가 실행되기 전까지는 관계를 맺지 않는다.

**JS에서 함수는 할당 가능하고 어디든 전달 가능한 값이라는 특징이 매우 중요**

- 함수형 패러다임을 지원하는 언어에서는 함수를 값으로 취급하는게 필수

매개변수(parameter)를 통해 함수에 값을 전달할 수 있다.

```javascript
function greeting(myName) {
  console.log(`${myName} 님 안녕하세요!`);
}

greeting('폴'); //폴 님 안녕하세요!
```

- 위 예시에서 myName이 매개변수이며 함수 내에서 지역 변수 역할을 함
- 함수는 0개부터 원하는 개수까지 원하는 만큼 매개변수를 받을 수 있도록 정의할 수 있음
- 함수를 호출할 때 인수(argument)라 부르는 값(예시에서는 "폴")을 매개변수에 할당한다.
- 함수는 오로지 한 개의 값만 반활할 수 있음, 여러개를 반환하고 싶다면 객체나 배열로 감싸 반환
- 함수는 값이므로 함수를 객체의 프로퍼티로 할당할 수 있음

#### 2.5 비교

#### 2.5.1 같음에 대한 고찰

- js에서 같음을 비교할 때는 **'정확하게'** 일치하는지를 따지기도 하지만 **'아주 유사'**하다거나 **'교환 가능'**한지와 같이 좀 더 넓은 관점에서 비교하는 떄도 있다.

**일치 비교**  
-일치 연산자(===)  
 단 일치 연산자가 특수한 값인 NaN(Not a Number) 이나 -0과 함꼐 사용되면 예상과 다르게 작동할 수 있다.

```javascript
NaN === NaN; // false
0 === -0; // true
```

- 일치 연산자는 NaN이나 -0과 함께 사용하지 않는게 최선  
  NaN을 비교할 때는 Number.isNaN() 을 사용  
  -0과 비교할 때는 Object.is() 를 사용  
  Object.is()는 NaN과의 비교에서도 사용 가능  
  따라서 일치 연산자만으로는 **"아주 정확하게"** 비교할 수 없다.

- 객체 비교

```javascript
[1,2,3] === [1,2,3]; //false
{a:42} === {a:42}    //false
(x => x *2) === (x => x *2) //false
```

- 일치 비교는 값의 본질(nature)이나 내용(content)을 비교
- 비교 대상이 객체인 경우 값의 본질이나 내용이 아닌 **구조적 일치**를 비교
- 객체 끼리 비교할 때 비교 연산자가 구조적 일치를 판단하지 않고 **독자성 일치**를 비교
- js객체는 참조에 의해 고정되며 참조 복사본을 사용해 할당, 전달 됨, 그리고 참조(독자성)을 대상으로 일치 비교가 일어남

```javascript
let x = [1, 2, 3]; //false

// 참조를 복사한 값이 할당되기 떄문에 변수 y는 x의 복사본이 아니다.
// 변수 y는 x와 '같은' 배열을 참조한다.
// 참조란 메모리에 할당된 영역

let y = x;

y === x; //true
y === [1, 2, 3]; //false
x === [1, 2, 3]; //false
```

**참조의 독자성** 중요

> 일단 책에서 참조에 대한 부분이 약간은 설명이 부족한 듯 싶어 추가
>
> ```javascript
> let x = [1, 2, 3]; //메모리 주소 0x001 할당되고 x는 메모리주소를 참조
> let y = x; // y는 위에 할당 된 x의 메모리 주소값을 참조하게 됨
>
> y === x; //이는 메모리 주소값이 같은 곳을 참조하기 떄문에 true
> ```
>
> ```javascript
> let a = [1, 2, 3]; // 메모리 주소 0x001 할당
> let b = [1, 2, 3]; // 메모리 주소 0x002 할당
> // a와 b는 객체의 값은 같으나 참조하는 메모리 주소가
> // 다르기 때문에 일치 비교연산 시 false를 반환하게 됨
> ```

- js에는 객체 구조가 같은지 비교할 방법이 없음, 같은 것을 참조하는지만 비교할 수 있음
- js에서는 객체 구조를 비교할 방법을 제공하지 않는다.

#### 2.5.2 강제 변환

- 한 타입의 값이 다른 타입의 값으로 변하는 걸 의미
- 타입강제 변환은 js를 지탱하는 커다란 기둥 중 하나  
  **동등 비교** -동등 연산자(==)는 피연산자의 타입을 비교한다. 단, 피연산자의 타입이 다른 경우 동등 연산자는 비교 이전에 강제로 타입을 맞추는 작업을 수행한다. (빡침포인트 1)  
  브랜던아이크(js창시자)가 동등 연산자 설계에는 큰 실수가 있다고 한탄한 바 있다고 함..후..

- 동등 연사자는 숫자형 피연산자를 선호함  
  예를 들어 42 == "42" 를 비교할 때 문자열을 숫자형으로 타입을 강제 변환하거나 1 == true 일 때 true를 1로 변환하는 형태..

- < , > , <= , >= 도 타입이 같으면 괜찮은데 다르면 강제 타입변환...(빡침포인트 2)
- 피연산자가 모두 문자열일 경우 알파벳순으로 문자열을 비교

```javascript
let x = '10';
let y = '9';

x < y; // true

// 이유 ? 문자열 "10"의 첫 문자는 "1" 이고, "9" 첫 번쨰 문자는 "9" 인데 js는 유니코드 값으로 비교하기 때문에 "1(유니코드 값: 49)"이고 "9(유니코드 값:57)" 이기 때문에 true
```

- 이런 강제 타입 변환 때문에 비교 연산자의 작동 방식을 제대로 배우고 받아들이는게 중요

#### 2.6 코드 구조화 패턴

- js 생태계 전반에 걸쳐 코드를 구조화하는 패턴은 크게 클래스와 모듈 두 가지가 있음
- 상호 배타적인 패턴이 아니기 때문에 두 패턴 모두를 사용함

#### 2.6.1 클래스

- 사용자가 정의한 데이터 '타입' 으로 데이터와 데이터를 조작하는 동작이 들어감, 다만 클래스는 사용자 정의 데이터 타입이 어떻게 동작하는지 정의하지만 구체적인 값은 아니며, 구체적인 값이 필요하다면 new 키워드를 통해 인스턴스를 만들어야 함.

- 클래스가 없어도 동일한 결과물을 만들수 있으나, 클래스를 사용하면 체계적이고 가독성이 좋은 코드를 만들 수 있다.

- 클래스 지향(객체 지향) 설계는 **상속**과 **다형성**을 뺴놓고 생각할 수 없다.

**상속**

- js에서 새로운 클래스를 정의할 때 기존의 클래스를 상속 받아 기능을 확장시킬 수 있는데 이때 사용하는 키워드는 **extends** 이다

**다형성**

- 상속받은 메서드와 새롭게 정의한 메서드의 이름이 동일하고 공존할 수 있는 것을 의미한다.

> ex) 상속과 다형성을 확인할 수 있는 예제 코드
>
> ```javascript
> // 부모 클래스
> class Publication {
>   constructor(title, author, pubDate) {
>     this.title = title;
>     this.author = author;
>     this.pubDate = pubDate;
>   }
>
>   print() {
>     console.log(`
>       제목 : ${this.title},  
>       저자 : ${this.author},  
>       발행일 : ${this.pubDate}  
>     `);
>   }
> }
> ```
>
> ```javascript
> // 자식 클래스 (부모 클래스를 상속 받았으니까)
> class Book extends Publication {
>   constructor(bookDetails) {
>     super(bookDetails.title, bookDetails.author, bookDetails.pubData);
>     this.publisher = bookDetails.publisher;
>     this.ISBN = bookDetails.ISBN;
>   }
>
>   print() {
>     super.print();
>     console.log(`
>       출판사 : ${this.publisher},
>       ISBN: ${this.ISBN}
>     `);
>   }
> }
>
> class BlogPost extends Publication {
>   constructor(title, author, pubDate, URL) {
>     super(title, author, pubDate);
>     this.URL = URL;
>   }
>
>   print() {
>     super.print();
>     console.log(`URL: ${this.URL}`);
>   }
> }
> ```
>
> ```javascript
> //자식클래스를 인스턴스화해서 사용하기
> let YDKJSY = new Book({
>   title: "You Don't Know JS Yet",
>   author: '카일 심슨',
>   publishedOn: '2020년 1월',
>   publisher: '독립 출판',
>   ISBN: '979-8602477429',
> });
>
> YDKJSY.print();
>
> // 결과
> // 제목 : You Don't Know JS Yet
> // 저자 : 카일 심슨
> // 발행일 : 2020년 1월
> // 출판사 : 독립 출판
> // ISBN : 979-8602477429
>
> let forBlog = new BlogPost(
>   'For and against let',
>   '카일 심슨',
>   '2024년 12월 31일',
>   'https://...'
> );
>
> forBlog.print();
>
> // 결과
> // 제목 : For and against let
> // 저자 : 카일 심슨
> // 발행일 : 2024년 12월 31일
> // URL : https://...
> ```

??문제 클래스에서 정의 된 함수는 뭐라고 할까요?

#### 2.6.2 모듈

- 클래스와 마찬가지고 논리적 단위 기준으로 데이터와 행동을 그룹화 하는데 목적이 있음
- 가장 큰 차이점은 문법
- ES6에서 공식적으로 추가됨 이전까진 자체적으로 패턴을 만들어 활용함

**클래식 모듈**

- 최소한 한 번 이상 실행되는 외부 함수
- 모듈 인스턴스 내부의 숨겨진 데이터를 대상으로 작동하는 함수가 있는 '인스턴스'를 반환
- 클래식 모듈은 **단순한 함수**이기도 하고 함수를 호출하면 모듈 인스턴스가 생성되기 떄문에 클래식 모듈 인스턴스에 있는 함수를 **모듈 팩토리** 라고 설명하기도 함

```javascript
//모듈팩토리 함수(클래식 함수) 정의
function Publication(title, author, pubDate) {
  let publicAPI = {
    print() {
      console.log(`
        제목 : ${this.title},  
        저자 : ${this.author},  
        발행일 : ${this.pubDate}  
      `);
    },
  };

  return publicAPI;
}

function Book(bookDetails) {
  let pub = Publication(
    bookDetails.title,
    bookDetails.author,
    bookDetails.publishedOn
  );

  let publicAPI = {
    print() {
      pub.print();
      console.log(`
        출판사 : ${bookDetails.publisher}
        ISBN : ${bookDetails.ISBN}
      `);
    },
  };

  return publicAPI;
}

function BlogPost(title, author, pubDate, URL) {
  let pub = Publication(title, author, pubDate);

  let publicAPI = {
    print() {
      pub.print();
      console.log(URL);
    },
  };

  return publicAPI;
}
```

```javascript
//모듈 팩토리(클래식 모듈) 함수를 인스턴스화해서 사용하기

let YDKJSY = Book({
  title: "You Don't Know JS Yet",
  author: '카일 심슨',
  publishedOn: '2020년 1월',
  publisher: '독립 출판',
  ISBN: '979-8602477429',
});

YDKJSY.print();

// 결과
// 제목 : You Don't Know JS Yet
// 저자 : 카일 심슨
// 발행일 : 2020년 1월
// 출판사 : 독립 출판
// ISBN : 979-8602477429

let forBlog = BlogPost(
  'For and against let',
  '카일 심슨',
  '2024년 12월 31일',
  'https://...'
);

forBlog.print();

// 결과
// 제목 : For and against let
// 저자 : 카일 심슨
// 발행일 : 2024년 12월 31일
// URL : https://...

//결과는 당연히 클래스와 같음 차이는 new키워드가 없을뿐
```

- 클래스는 메서드와 데이터를 객체 인스턴스에 저장하며, 메서드와 데이터에 접근하려면 접두사 this.를 사용해야 함
- 모듈에서는 this.없이 도 스코프 내 식별자 역할을 하는 변수를 사용해 메서드와 데이터에 접근
- 외부에 노출된 공개 메서드를 사용해 객체를 명시적으로 만들고 반환한다. 이때 데이터나 참조되지 않은 메서드는 팩토리 함수 내에 비공개로 남는다.

1. 예시에서 외부에 노출된 메서드 ?  
   1.1 Publication 함수의 print 메서드  
   1.2 Book 함수의 print 메서드
   1.3 BlogPost 함수의 print 메서드

2. 예시에서 비공개로 남는 데이터나 참조되지 않는 메서드 ?  
   2.1 비공개 데이터 : title, author, pubDate, bookDetails  
   2.2 비공개 메서드 : Publication 객체의 print 메서드

**ES 모듈**

- 구현관점에서 ES모듈과 클래식 모듈의 접근법에는 큰 차이가 있다.
- ES 모듈은 클래식 모듈과 동일한 취지를 갖는 문법
- AMD, UMD, CommonJS의 주요 변형과 그 용례를 고려해 만들어짐

**차이점**

1. ES모듈에는 모듈을 정의하는 래핑 함수가 없다.
2. ES모듈을 사용할 떄 모듈 API와 직접 상호작용하지 않는다.  
   export 키워드를 사용해 변수나 메서드를 퍼블릭 API로 정의한다. 모듈 내에 변수나 메서드라도 export 키워드가 없으면 비공개 처리 됨
3. ES모듈을 인스턴스화하지 않아도 import 키워드를 사용해 가져오기만 하면 단일 인스턴스처럼 사용할 수 있다.  
   import 키워드를 사용해 처음 모듈을 가져온 순간 인스턴스가 생성되고, 동일한 모듈을 다른 곳에서 import 할 때는 이미 생성된 모듈의 참조(메모리 주소값)만 가져온다.

> 문제
>
> <details>
>  <summary>Q1. JS에서 값은 크게 어떻게 나뉠까요?
> </summary>
> <br/>
>  <p>A 1. 원시타입과 객체타입</p>
> </details>
> <br/>
> <details>
>  <summary>Q2. JS에서 백틱(`)으로 감싼 문자열에 변수표현식을 사용하는 방식을 뭐라고 하나요? 
> </summary>
> <br/>
>  <p>A2. 보간법</p>
> </details>
> <br/>
> <details>
>  <summary>Q3. JS에서 원시타입에는 어떤게 있나요?
> </summary>
> <br/>
>  <p>A3. JS의 원시 타입 종류 - string, number, boolean, null, undefined, symbol, bigint</p>
> </details>
> <br/>
> <details>
>  <summary>
>  Q4. 아래의 코드의 console.log의 결과값은?<br/>
> var myName = "폴"; <br/>
> var yourName = myName; <br/>
> myName = "망푸"; <br/>
> 1. console.log(myName); <br/>
> 2. console.log(yourName); <br/>
> </summary>
> <br/>
>  <p>
>   A4. 1. 망푸, 2. 폴
>   <br/>
>   -원시타입의 값이 독립적인 것에 대한 증명(부록 A.1) 
> </p>
> </details>
> <br/>
> <details>
>  <summary>Q5. JS의 변수 선언 시 var과 let의 접근 범위는 어떻게 되나요?
> </summary>
> <br/>
>  <p>A5. 함수스코프, 블록스코프</p>
> <p>2.3 변수 선언과 사용 60P 참조</p> 
> </details>
> <br/>
