# Understandable
Understandable은 사용자가 UI와 정보를 쉽게 이해하고 운용할 수 있는지에 관한 항목이다.

글의 가독성, 예측 가능한 조작, 사용자의 실수를 도울 수 있는 지원 이 3가지를 기준으로 
접근성을 준수하고 있는지 가이드라인을 제시하고있다.

## 1. 글의 가독성
텍스트 콘텐츠를 읽을 수 있고 이해할 수 있어야 한다.

### 1.1 페이지의 언어

웹페이지의 기본언어를 제공해야 한다.

### 의도:
사용자 에이전트가 텍스트 및 기타 언어 콘텐츠를 올바르게 표시하여 장애가 있는 사용자들이 그 내용을 더 잘 이해할 수 있게 한다.

#### 사례

설명: html 태그 내에 lang 속성 사용

<div style="text-align: center">
    <img src="images/language-page.PNG"/>
    <cite>
        <a href="https://www.naver.com">lang 속성을 사용 예시</a>
        by NAVER
    </cite>
</div>

### 1.2 부분 언어
적절한 단어, 전문 용어, 불확실한 단어, 모국어의 방언을 사용하는 경우를 제외하고 사용자 에이전트가 콘텐츠를 올바르게 표시할 수 있어야 한다. 본 언어를 인지할 수 있게 부분적으로 제공해야 한다.

#### 의도:
여러 언어로 작성된 내용이 각각 어떤 언어인지 올바르게 표시해서 사용자 에이전트와 보조 기술들이 해당 언어를 올바르게 표현하고 발음하도록 한다.

#### 적용가능 기술:
- lang 속성을 사용해 특정언어 기제
- HTML DOM에서 언어를 부분적으로 지정하도록 silverlight object 선언

#### 사례

설명: 영어 사전에서 한국어와 영어를 나누어 표기

<div style="text-align: center">
    <img src="images/language-parts.PNG"/>
    <cite>
        <a href="https://en.dict.naver.com/#/entry/enko/b329d0e24f9b4de1af1f7eb9ad023966">
        lang 속성을 부분적으로 사용한 예시</a>
        by NAVER
    </cite>
</div>

### 1.3 생소한 단어
방언이나 전문 용어와 같은 특수한 언어나 구절을 인지할 수 있는 메커니즘을 제공해야 한다.

#### 사례

설명: 홈텍스는 특수 용어에 대한 해설을 용어사전이라는 메커니즘으로 제공한다.

<div style="text-align: center">
    <img src="images/unusual-word.PNG"/>
    <cite>
        <a href="https://txsi.hometax.go.kr/docs/customer/dictionary/wordList.jsp">용어 사전</a>
        by 홈텍스
    </cite>
</div>

### 1.4 약어
약어의 의미를 인지할 수 있는 메커니즘을 제공해야 한다.

#### 적용가능 기술
- 동일한 웹페이지에서 약어가 가지는 의미가 유일한 경우
    - 확장가능한 형태의 폼으로 약어의 본 뜻을 해설한다.
    - 용어의 본 뜻을 설명하는 링크를 연결한다.
    - abbr 태그를 사용해 본 뜻을 해설한다.
    - 용어사전을 제공한다.
    - 용어를 검색하기 위한 온라인 사전을 제공한다.
- 동일한 웹페이지에서 약어가 가지는 의미가 여러개인 경우
    - 용어의 뜻을 설명하는 링크를 연결한다.
    - abbr 태그를 사용해 본 뜻을 해설한다.

#### 사례

### 1.5 독해 수준
콘텐츠는 최대한 간단 명료하게 작성해야 하고, 만약
중학교 수준 이상의 독해능력이 필요한 경우는 충분히 해설가능한 보충 콘텐츠를 제공해야 한다.

#### 의도:
독서 장애를 가진 사람들을 돕고. 저자가 풀이하기 어려운 콘텐츠를 비교적 쉽게 이해할 수 있도록 한다.


#### 적용가능 기술:
- 요약본 제공: 이해하기 어려운 복잡한 텍스트를 이해할 수 있는 짧은 요약본으로 제공한다.
- 아이이어, 이벤트, 프로세스를 설명하는데 도움이 되는 시각적인 그림 및 기호를 제공한다.
- 

#### 사례

설명: 삼성 뉴스 페이지의 summary 제공

<div style="text-align: center">
    <img src="images/unusual-word.PNG"/>
    <cite>
        <a href="https://news.samsung.com/global/samsung-introduces-galaxy-tab-s-a-super-amoled-tablet">요약본 제공 예시</a>
        by 삼성
    </cite>
</div>