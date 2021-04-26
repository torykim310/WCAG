# Part 4. 견고성(Robust)

## 이 글의 목적와 순서

이 글에서는 Accessibility Guidelines Working Group에서 발행한 WCAG(Web Content Accessibility Guidelines) 중 네 번재 주제인 '견고성((Robust)'의 내용을 정리하고 해당 가이드라인을 잘 준수한 웹 사이트를 사례로 소개하려고 한다. 이 글은 다음 순서로 전개해가고자 한다.

1. WCAG 중 견고성((Robust)을 준수하기 위한 기준 소개
2. 각 기준을 준수한 웹 사이트 소개

## 1. WCAG 중 견고성(Robust) 내용 소개

견고성은 보조장치를 포함한 다양한 사용자 에이전트가 콘텐츠를 올바르게 해석할 수 있도록 견고하게 콘텐츠를 작성해야 함을 의미한다. WCAG에서는 견고성을 평가하는 기준을 다음과 같이 1가지로 제시하고 평가의 단계를 세 가지(A, AA, AAA)로 구분한다.

- 호환성(Compatible)

### 2.1 평가 기준 1 - 호환성(Compatible)
보조장치를 포함하여 사용자 에이전트가 현재와 미래에 웹과 호환될 수 있도록 설계해야 한다.

#### 2.1.1 충족기준

#### 1. 파싱(Parsing) - A
보조장치를 포함한 사용자 에이전트가 내용을 정확하게 해석하고 분석할 수 있어야 한다. 에이전트가 HTML문서를 분석할 수 없는 경우 "복구 기법"을 통해 문서를 유추하여 내용을 전달한다.

복구 기법은 사용자 에이전트마다 다르기 때문에 정확한 정보를 전달할 수 없게 된다. 따라서 요소의 시작과 끝을 올바르게 작성하고, 마크업 구조만으로 사용자 에이전트가 올바르게 분석할 수 있도록 설계해야 한다.

#### 적용가능 기술:
- [G134](https://www.w3.org/WAI/WCAG21/Techniques/general/G134.html):validating web page: 마크업 문법 규정 및 W3C에서 제공하는 표준을 준수했는지 검사할 수 있는 웹 서비스를 활용한다.

#### 2. 이름, 역할, 값(Name, Role, Value) - A
프로그램 상 웹 페이지 내에 모든 구성 요소가 name, role, value 이 3가지를 가져야 한다. 일반적인 경우 스크린리더는 각 요소의 이름, 역할 , 값을 분석해서 사용자에게 메세지를 전달한다. 웹 표준을 지킨경우 위 조건을 자동적으로 충족하기 때문에 이 기준을 통과하지만 웹 표준을 벗어나 자신만의 규칙을 설정하여 개발할 경우에는 적합한 기술을 사용하여 사용자에게 메세지를 전달할 수 있게 설계해야 한다.

#### 적용가능 기술:
- Situation A: 표준 마크업 언어를 사용한 경우
    - [ARIA14](https://www.w3.org/WAI/WCAG21/Techniques/aria/ARIA14.html): `label` 태그를 사용할 수 없는 경우, `aria-label`을 대신 사용할 수 있다.
    - [ARAI16](https://www.w3.org/WAI/WCAG21/Techniques/aria/ARIA16.html): `aria-labelledby` 속성을 사용한다.
    - [G108](https://www.w3.org/WAI/WCAG21/Techniques/general/G108.html): 마크업 태그와 속성을 사용해 이름, 역할, 값을 설정한다.
- Situation B: 웹 표준에 지정된 원래 용도를 변경해서 사용한 경우
    - ARAI16
- Situation C: 웹 표준을 벗어나 자신만의 고유한 컴포넌트를 생성한 경우
    - [ARIA5](https://www.w3.org/WAI/WCAG21/Techniques/aria/ARIA5.html): WAI_ARIA의 state 혹은 property를 사용 알맞은 이름, 역할, 값을 설정한다.
        ul를 토글 버튼으로 사용하고자 할 때, role="button", aria-pressed="false", aria-lablelledby="bold_label" 과 같은 방식으로 ul 컴포넌트의 속성을 변경할 수 있다.

#### 3. 상태 메시지(Status Messages) - AA
상태 메세지란 사용자에게 중요한 메세지이지만 초점을 변경할 정도로는 중요하지는 않은 새로운 콘텐츠다. 일반적으로 스크린리더는 위에서 아래로 왼쪽에서 오른쪽으로 흐름에 맞게 읽어주거나 포커스 상태가 되어야 읽어주기 때문에 새 콘텐츠를 읽어줄 수 없다. 따라서 적절한 기술을 사용해서 새 콘텐츠를 사용자에게 읽어줄 수 있게 설계해야 한다.

#### 적용가능 기술:
- Situation A: 상태 메세지가 작업의 성공과 실패와 같은 결과를 알려주는 경우
    - [ARIA22](https://www.w3.org/WAI/WCAG21/Techniques/aria/ARIA22.html): `role` 속성을 `status`로 설정한다. 이는 암묵적으로 `aria-live="polite"`속성을 설정하기 때문에 현재 출력하고있는 음성메세지가 끝났을 때 새 컨텐츠를 읽어줍니다.
-Situation B: 상태 메세지가 오류 혹은 경고를 전달하는 경우
    - [ARIA19](https://www.w3.org/WAI/WCAG21/Techniques/aria/ARIA19.html): `role` 속성을 `alert`로 설정한다. 이는 암묵적으로 `aria-live="assertive"`속성을 설정하기 때문에 현재 출력하고있는 음성메세지를 멈추고 새 컨텐츠를 읽어줍니다.
    `window.alert`와의 차이점은 포커스가 이동하지 않아도 사용자에게 메세지를 전달한다는 점 입니다.
-Situation C: 상태 메세지가 프로세스 진행에 대한 정보를 전달하는 경우
    - [ARIA23](https://www.w3.org/WAI/WCAG21/Techniques/aria/ARIA23.html): `role` 속성을 `log`로 설정한다. 이는 암묵적으로 `aria-live="polite"`속성을 설정하기 때문에 현재 출력하고있는 음성메세지가 끝났을 때 새 컨텐츠를 읽어줍니다. ARIA19, ARIA 22와의 차이점은 `aria-atomic=false`로 설정되어있기 때문에 log가 부분적으로 변경된 경우 변경된 내용만 읽어줍니다.
    - ARIA22 + G193: `role="state"` + 보조장치(avatar)

### 소결론
견고성에 대해 학습하고 사례를 찾아보면서 견고성을 준수하고있는 사이트가 거의 없다는 것을 알게됐다. 고의가 아니라 견고성에 대한 지식을 접하지 못해서 그릇된 정보를 전달할 수 도 있을 것이라는 생각이 들었다. 이번 과제를 통해 견고성에 대한 지식을 알릴 수 있는 기회가 많아졌으면 좋겠다고 생각했다. 다른사람들에게 접근성에 대해 설명할 수 있을 정도로 꾸준히 학습해야겠다.

#### 참고자료
- [Status Message](https://www.youtube.com/watch?v=Bsj2s58GvVA&list=PLtaz5vK7MbK1bAGhAFkidBzIRVrNqVo5j&index=19)
