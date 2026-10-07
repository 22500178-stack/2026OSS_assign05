22500178 김지원

# 이번 주에 배운 핵심 내용 3가지
- DOM (Document Object Model): HTML 문서를 브라우저가 이해할 수 있는 객체 트리 구조로 표현한 것이다.
- 이벤트 처리 (Event Handling): 사용자 클릭, 입력 등의 동작을 감지하고 원하는 동작을 실행하는 기능이다.  
- 동적 요소 조작 & Form 제어: JS로 화면 요소를 직접 생성·삭제하거나 Form 입력값을 검증하는 작업이다.  

# CRUD Service
## 구현한 서비스 주제: 
러닝 기록 관리 CRUD 웹 서비스
## v사용하는 데이터 Field: 
id, date(날짜), distance(km), time(분), pace(페이스, min/km), note(러닝장소 메모)
## C,R,U,D 구현 방법:
- Create: <form> 제출 이벤트를 감지하여 입력값을 읽어온 뒤 runs.push()로 배열에 새 객체를 추가한다.
- Read: 배열(runs)을 순회하는 render() 함수를 만들어 HTML <table> 내부 <tbody>에 데이터 행을 출력한다.
- Update: [수정] 버튼 클릭 시 startEdit(id)로 해당 데이터의 기존 값을 Form 입력창에 채우고, 제출 시 runs.find()로 대상을 찾아 객체 값을 직접 변경한다.
- Delete: [삭제] 버튼 클릭 시 runs.filter()를 활용하여 해당 id와 일치하지 않는 데이터만 남긴 새 배열로 갱신한다.


# 이번 과제에서 사용한 주요 JavaScript 기능을 설명합니다.
- document.getElementById(): HTML element(테이블 body, Form 등)의 DOM 요소에 접근하기 위해 사용했습니다.
- addEventListener(): Form 제출(submit) 이벤트를 감지하여 페이지 새로고침(e.preventDefault())을 막고 데이터 추가/수정 함수를 실행합니다.
- createElement() & appendChild(): 데이터를 화면에 출력할 때 dynamic하게 <tr> 행 요소를 생성하고 <tbody> 자식 요소로 조립했습니다.
- Array.prototype.forEach(): runs 배열 전체를 순회하며 화면에 데이터를 매번 새로 그려주는 render() 기능에 사용했습니다.
- Array.prototype.filter(): 삭제 로직 수행 시 클릭한 id와 다른 항목만 추출하여 기존 데이터를 지우는 목적으로 사용했습니다.
- Array.prototype.find(): 수정할 데이터를 찾거나 Form에 기존 정보를 채워 넣을 때 해당 id의 객체를 단건 조회하기 위해 사용했습니다.
- render() (사용자 정의 함수): tbody.innerHTML = ""로 기존 화면을 비운 뒤 최신 배열 데이터를 처음부터 다시 출력하여 화면-데이터 동기화를 유지합니다.

# AI / Search Usage
- 사용한 AI 또는 검색 도구: Gemini
- 아직 JavaScript 언어 문법과 흐름이 익숙지 않아 코드를 100% 작성하는 데 어려움이 있었으나, AI를 활용해 가이드 코드를 작성받고 코드의 전체적인 구조를 이해하는 데 많은 도움을 받았다. 또한 AI가 설명해 주는 코드의 동작 원리와 흐름을 바탕으로, 직접 코드 구문마다 주석을 달아보며 각 줄이 의미하는 바를 확실하게 파악하려고 노력하였다.

# Problem & Solution
- [Add] 버튼을 누르면 화면이 엑셀처럼 착 바뀌지 않고, 웹페이지가 새로고침되면서 써놓은 내용이 날아가는 문제를 버튼을 누를 때 브라우저가 자기 마음대로 페이지를 새로고침하지 못하게 막아주는 명령어(e.preventDefault())를 코드 맨 위에 적어서 해결했다.
- 새로운 기록을 추가할 때마다 화면에 이전 데이터까지 중복으로 2번, 3번씩 계속 밑에 붙어서 나오는 문제를 화면에 목록을 보여주기 바로 직전에 기존에 그려져 있던 내용들을 싹 비워주는 줄(tbody.innerHTML = "")을 추가해서 해결했다.

# Reflection 이번 과제를 통해 새롭게 알게 된 점 또는 궁금한 점
JavaScript는 원본 HTML 파일을 직접 고치는 것이 아니라, 브라우저가 생성한 메모리 상의 DOM 객체 구조를 조작하여 화면을 동적으로 바꾼다는 점을 알게되었다.
또한 단순히 HTML 구조를 짜는 웹 페이지 제작에서 벗어나, JavaScript를 통해 사용자의 클릭이나 입력에 실시간으로 반응하는 동적 웹을 만들어 보았는데, 아직 JavaScript언어가 익숙하지 않아 쉽지는 않았지만 한 동작에 대해 반응이 되는 페이지를 만드니 조금 흥미를 느꼈다.