---
title: html, css
categories: BoostCourse
tags: [부스트코스, 웹프로그래밍, HTML, CSS]
excerpt:
---
# HTML
- 각 태그를 용도에 맞게 사용해야함 (접근성)
- 시맨틱태그 (레이아웃)
    - header
    - section
    - nav
    - footer
    - aside
- HTML 구조 설계
    - CSS 코드 작성 전에 HTML 구조를 먼저 설계
    - 큰 영역에서 작은 영역으로 좁혀서 완성
- CLASS & ID
    - class 속성 : 한 문서에서 여러개의 요소를 가질 수 있음
    - id 속성 : 한 문서에 단 하나의 요소만 가질 수 있음
    
# CSS
`selector { property: value; }`
- 선언방법
    - inline 방식 : 각 태그에 style 속성으로
    - internal 방식 : head 태그 안에 style 태그로
    - external 방식 : 외부 css 파일로  
    ex) `<link rel="stylesheet" type="text/css" href="path">`
- 상속
    - 상위 태그에 적용한 스타일은 하위 태그에도 반영
    - box-model 속성 (width, height, margin, padding, border)은 상속 안됨
- 우선순위 (cascading)
    - inline -> internal, external
    - 구체적인 것 (div > p -> p)
    - id > class > element
    - 우선순위가 동일한 것은 나중에 선언된 것으로 적용
- 선택자
    - 태그 : 태그명 그대로 씀
    - #id : id 선택  
    ex) `#myid { color : red; }`
    - .class : class 선택  
    ex) `.myclass { color : blue; }`
    - a, b, c : 여러 요소 한번에 선택  
    ex) `span, div#id, a { color : yellow;}`
    - a b : 하위요소 선택  
    ex) `#id span { color : green; }`
    - a > b : 자식요소 선택  
    ex) `div > p { color : white; }`
    - nth-child : 모든 자식 중 n번째 자식요소  
    ex) `#myid > p:nth-child(2) { color : black; }`
    - nth-of-type : 해당하는 태그 중 n번째 요소  
    ex) `p:nth-of-type(3) { color : purple; }`
- 기본스타일
    - font 색상 변경  
    ex)  
    `{color: red;}`  
    `{color: rgba(255, 0, 0, 0.5);}`  
    `{color: #ff0000;}`
    - font 사이즈 변경  
    ex)  
    `{font-size: 16px;}`  
    `{font-size: 1em;}`  
    *1em = 상위노드의 폰트사이즈*
    - 배경색  
    ex)  
    `{background-color: #ff0;}`
        - background-image, position, repeat등의 속성 有  
        축약형 ex) `{background: #0000ff url(".../gif") no-repeat center top;}`
    - 글꼴  
    ex)  
    `{font-family: "Gulim";}`  
    `{font-family: monospace;}`  
    폰트명에 띄어쓰기가 있으면 따옴표로 묶어줌
- 웹폰트
    - 브라우저에서 지원하지 않는 폰트를 웹에서 다운로드받아 사용
    - 다운로드 시간이 오래걸릴 수 있고 다양한 해상도에서 문제가 발생할 수 있음
- 레이아웃
    - [참고사이트](https://ko.learnlayout.com/)
    - display
        - block : 위에서 아래로 배치
        - inline : 좌에서 우로 배치, 높이와 넓이 반영안됨
        - inline-block : 좌에서 우로 배치, 높이와 넓이 반영됨
        - ex) span, a, strong 태그 등
        - none : 화면상 보이지 않음
    - position
        - top, left, right, bottom으로 위치를 설정  
        ex) `{position: absolute; top: 15px;}`
        - static : 기본속성, 순서대로 배치
        - relative : 원래 자신이 위치해야할 곳을 기준으로 이동
        - absolute : 기준점에 따라 특별한 위치로 이동, 상위 요소 중 static이 아닌 position이 기준점(relative 등)
        - fixed : viewport(전체화면, body) 좌측, 맨 위를 기준으로 이동
    - float
        - 원래 위치에서 둥둥 떠있는 상태
        - float된 요소뒤의 block 요소는 float된 요소를 인식하지 못하고 중첩돼서 배치됨
    - clear
        - float된 요소에 float 속성을 지움
    - box-model
        - border : 테두리 굵기
        - margin : 위, 아래, 좌우 요소와 자신 사이의 간격  
        ex)  
        작성할 때는 시계방향으로 위, 우측, 아래, 좌측 순  
        `{margin: 5px 15px 5px 10px;}`  
        또는 위아래, 좌우측 순  
        `{margin: 10px 15px;}`

        - padding : 테두리와 내용 사이의 간격
        - width, height : box의 넓이, 높이  
        width, height = border + padding + content
        - box-sizing
            - box 크기 = margin + width, height
            - content-box : box-sizing 기본값, border, padding이 늘어나면 box 크기가 늘어남
            - border-box : border, padding이 box 크기를 늘리지 않음
