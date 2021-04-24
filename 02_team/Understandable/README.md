# Part 3. 이해의 용이성(Understandable)

## 이 글의 목적와 순서

이 글에서는 Accessibility Guidelines Working Group에서 발행한 WCAG(Web Content Accessibility Guidelines) 중 세 번재 주제인 '이해의 용이성(Operable)'의 내용을 정리하고 해당 가이드라인을 잘 준수한 웹 사이트를 사례로 소개하려고 한다. 이 글은 다음 순서로 전개해가고자 한다.

1. WCAG 중 이해의 용이성(understandable)을 준수하기 위한 기준 소개
2. 각 기준을 준수한 웹 사이트 소개



## 1. WCAG 중 이해의 용이성(Understandable) 내용 소개
이해의 용이성은 웹 페이지를 이용하는 사용자가 UI와 정보를 쉽게 이해하고 운용할 수 있음을 의미한다. 이해의 용이성이라 함은 장애가 없는 일반인의 입장에서는 물론 시각, 청각, 지적 장애 등을 가지고 있는 장애인의 입장에서도 웹 페이지의 구성요소들을 **이해**할 수 있어야 한다는 것이다. WCAG에서는 이해의 용이성을 평가하는 기준을 다음과 같이 3가지로 제시하고 평가의 단계를 세 가지(A, AA, AAA)로 구분한다.

- 글의 가독성(Readable)
- 예측 가능한 조작(Predictable):
- 입력 지원(Input Assistance) : 사용자가 실수 도울 수 있는 지원

### 2.1 평가 기준 1 - 글의 가독성(Readable)

#### 2.1.1 성공기준 

#### 1. 페이지의 언어(Language of Page) - A
페이지의 텍스트 및 기타 언어 콘텐츠를 올바르게 표시하여 사용자 에이전트가 페이지에 표기된 언어를 바르게 읽을 수 있도록 한다. 이는 장애가 있는 사용자들에게도 보조 기기를 통해 정보를 올바르게 전달할 수 있다.

#### 사례

<figure>
    <figcaption>
        <cite><a href="https://www.naver.com">html 태그 내에 lang 속성 사용</a> - by NAVER</cite>
    </figcaption>
    <img src="images/language-page.PNG" width=100%/>
</figure>

#### 2. 부분 언어(Parts of Language) - AA
단어 자체가 적절한 경우, 전문 용어, 불확실한 단어, 모국어의 방언을 사용하는 경우를 제외하고 사용자 에이전트가 콘텐츠를 올바른 언어로 받아 들일 수 있어야 한다. 즉 페이지 내에서 여러 언어를 사용했다면 프로그램 상 각 언어마다 어떤 언어인지 올바르게 표시해서 사용자 에이전트와 보조 기술들이 해당 언어를 올바르게 표현하고 발음하도록 해야 한다.

#### 적용가능 기술:
- lang 속성을 사용해 특정언어 기제
- HTML의 DOM이 언어를 부분적으로 지정하도록 silverlight object 선언

#### 사례

<figure>
    <figcaption>
        <cite><a href="https://en.dict.naver.com/#/entry/enko/b329d0e24f9b4de1af1f7eb9ad023966">영어 사전에서 lang 속성을 부분적으로 사용한 예시 - </a>
        by NAVER
    </figcaption>
    <img src="images/language-parts.PNG" width=100%/>
</figure>

#### 2. 생소한 단어(Unusual words) - AAA
방언이나 전문 용어와 같은 특수한 언어나 구절을 인지할 수 있는 메커니즘을 제공해야 한다.

#### 적용가능 기술
- 동일한 웹페이지에서 용어가 가지는 의미가 유일한 경우
    - dl(description lists) 태그를 사용해 본 뜻의 정의를 해설한다.
    - dfn 태그를 사용해 정의를 제공한다.
    - 용어사전을 제공한다.
    - 용어를 검색하기 위한 온라인 사전을 제공한다.
- 동일한 웹페이지에서 용어가 가지는 의미가 여러개인 경우
    - 용어사전이나, description list로 의도한 뜻을 연결한다.
    - dfn 태그를 사용해 정의를 제공한다.

#### 사례
<figure>
    <figcaption>
        <cite><a href="https://txsi.hometax.go.kr/docs/customer/dictionary/wordList.jsp">특수 용어사전을 메커니즘으로 제공 </a> -
        by 홈텍스
    </figcaption>
    <img src="images/unusual-word.PNG" alt="홈텍스 용어사전" width=100%/>
</figure>

#### 4 약어(Abbreviations) - AAA
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
<figure>
    <figcaption>
        <cite><a href="https://txsi.hometax.go.kr/docs/customer/dictionary/wordList.jsp">확장가능한 현태의 폼으로 약어의 본 뜻을 해설</a> - by Youtube
    </figcaption>
    <img src="images/Abbreviations.PNG" alt="Surf Mesa-liy" width=100%/>
</figure>

#### 5 독해 수준(Reading Level)
콘텐츠는 최대한 간단 명료하게 작성해야 하고, 만약
중학교 수준 이상의 독해능력이 필요한 경우는 충분히 해설가능한 보충 콘텐츠를 제공해야 한다. 이는 독서 장애를 가진 사람들을 돕고. 저자가 풀이하기 어려운 콘텐츠를 비교적 쉽게 이해할 수 있도록 한다.

#### 적용가능 기술:
- 요약본 제공: 이해하기 어려운 복잡한 텍스트를 이해할 수 있는 짧은 요약본으로 제공한다.
- 아이디어, 이벤트, 프로세스를 설명하는데 도움이 되는 시각적인 그림 및 기호를 제공한다.
- 오디오 형식으로 콘텐츠를 제공한다.
- 텍스트를 쉽게 작성한다.
    - 단락당 주제를 설정한다.
    - 긴 문장을 사용하지 않는다.(영어 기준 25단어)
    - 긴 문장을 두개의 문장으로 나눈다.
    - 두개 이상의 접속사를 한 문장에 사용하지 않는다.
    - 전문 용어, 은어 및 명확하지 의미의 용어는 피한다.
    - 의미가 변하지 않는다면 중복된 단어를 제거한다.


#### 사례

설명: 삼성 뉴스 페이지의 summary 제공

<figure>
    <figcaption>
        <cite><a href="https://news.samsung.com/global/samsung-introduces-galaxy-tab-s-a-super-amoled-tablet">삼성 뉴스 페이지의 요약본 제공</a> - by Samsung
    </figcaption>
    <img src="images/summary.PNG" alt="Surf Mesa-liy" width=100%/>
</figure>

#### 6. 발음(Pronunciation) - AAA
약어와 같이 그 특수한 발음을 알지 못하면 단어의 의미를 알기 힘든 경우에 메커니즘을 제공해야 한다.

#### 적용가능 기술:
- 웹페이지 내에서 최소한 단어의 첫 등장시에 한번은 사용자가 이해가능한 발음을 제공한다. 단, 철자는 같지만 발음이 다른 단어가 포함된 경우 이 기술은 부적절 하다.
- 발음을 들을 수 있는 링크를 제공한다.
- 발음을 들을 수 있는 용어 사전을 제공한다.
- ruby 태그를 통해 발음을 제공한다.


#### 사례