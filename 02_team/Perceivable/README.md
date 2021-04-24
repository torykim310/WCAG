# Perceivalbe

## 1. 대체 텍스트의 제공

> Provide text alternatives for any non-text content so that it can be changed into other forms people need, such as large print, braille, speech, symbols or simpler language.

간단하게 요약하자면, 텍스트로 이루어진 컨텐츠가 아닌 경웨는 대체 텍스트를 제공해야 한다는 것이다. 대체 텍스트를 제공해야 하는 이유는 다음과 같이 명시되어 있다.

<figure style="text-align:center">
  <figcaption>[ Intent for Text Alternatives ]</figcaption>
  <img src="./img/text-alt-intent.png" width="900">
</figure>

위 설명을 보면 대체 텍스트는 어떠한 정보에 접근할 수 있는 가장 주가 되는 방법이고, 따라서 대체 텍스트를 통해서 청각 장애인이 소리 대신 텍스트로 정보에 접근할 수 있도록 하며 시각 장애인은 대체 텍스트를 읽어주는 보조 기기를 통해서 정보에 접근할 수 있도록 해줄 수 있다고 되어 있다.

예를 들어서 아래와 같은 데이터 차트가 있다고 가정해보자.

<figure style="text-align:center">
  <figcaption>[ Sample Data Chart ] (W3C)</figcaption>
  <img src="./img/data-chart.png" width="600">
</figure>

대부분의 사용자들은 해당 정보를 문제없이 이해하고 파악할 수 있을 것이다. 하지만 컨텐츠에 접근성에 대한 고려가 되어있지 않다면 시각 장애인의 경우 해당 컨텐츠에 대해서 전혀 접근할 수 없기 때문에 아래와 같이 대체 텍스트가 제공되어야 한다는 것이다.

```html
<img
  src="chart.png"
  alt="Bar chart showing monthly and total visitors for the first quarter 2014 for sites 1 to 3. Described under the heading Site visitors full text."
/>
<p class="a11y-hidden">Site 1 : January 140, ...</p>
```

이러한 방식으로 대체 텍스트를 제공해주어 `non-text content`에 대한 접근성을 확보해줄 수 있다.

## 2. 멀티미디어의 대체 수단

> Provide alternatives for time-based media.

오디오, 동영상의 경우에는 시각 장애인과 청각 장애인 모두에게 접근성이 떨어진다. 따라서 오디오나 동영상의 경우에는 `track` 태그를 통해서 자막(텍스트)을 제공해주어야 한다.

<figure style="text-align:center">
  <figcaption>[ Sample Video ] (MDN)</figcaption>
  <img src="./img/video-example.png" width="400">
</figure>

```html
<video id="video" controls preload="metadata">
  <source src="example.mp4" type="video/mp4" />
  <source src="example.webm" type="video/webm" />
  <track
    src="sub_kr.vtt"
    kind="subtitles"
    srclang="ko"
    label="Korean"
    default
  />
  <track src="sub_en.vtt" kind="subtitles" srclang="en" label="English" />
  <track
    kind="descriptions"
    src="sampleDescriptions_en.vtt"
    srclang="en"
    label="English"
  />
  <track
    kind="descriptions"
    src="sampleDescriptions_ko.vtt"
    srclang="ko"
    label="Korean"
  />
</video>
```

이러한 `track` 태그에는 다음과 같은 속성값들이 존재한다

- `captions`

  - 텍스트 트랙이 대화 및 음향 효과에 관한 것임을 명시함
  - 청각장애인을 위한 트랙에 적합

- `chapters`

  - 텍스트 트랙이 챕터의 제목임을 명시함.
  - 미디어 리소스의 탐색에 적합함

- `descripotions`

  - 텍스트 트랙이 비디오 콘텐츠에 대한 텍스트 설명임을 명시함.
  - 시각장애인을 위한 트랙에 적합함

- `metadata`

  - 텍스트 트랙이 스크립트에 사용되는 콘텐츠임을 명시하며, 사용자에게는 보이지 않음.

- `subtitles`
  - 텍스트 트랙이 비디오 콘텐츠의 자막임을 명시함.

## 3. 명료성

> Create content that can be presented in different ways (for example simpler layout) without losing information or structure
>
> Make it easier for users to see and hear content including separating foreground from background.

간단히 요약하자면 정본, 구조 등이 손실없이 다른 방법들로 표현될 수 있도록 컨텐츠를 만들어야 한다는 것이다. 그리고 w3c - WCAG에 따르면 정보들은 색상, 크기 등의 시각적인 효과 등에만 의존하면 안되고, 화면의 가로나 세로 등의 특정 방향으로만 적용되면 안된다. 또한 사용자가 컨텐츠를 더 쉽게 볼 수 있도록 해야한다.

<figure style="text-align:center">
  <figcaption>[ Chart Color/Black ]</figcaption>
  <img src="./img/chart-color-black.png" width="600">
</figure>

예를 들어서 위 사진을 보면, 일반 사용자들은 빨간색과 파란색 선을 보고 차트를 이해하고 분석할 수 있지만 색깔을 구분하지 못하는 저시력자는 표을 이해하지 못해 제공되는 대체 텍스트를 보거나 보조기기를 활용해 내용을 파악해야할 것이다. 하지만 아래 표를 보자.

<figure style="text-align:center">
  <figcaption>[ Chart Black ]</figcaption>
  <img src="./img/chart-black.png" width="600">
</figure>

해당 그래프는 색과 상관 없이 차트를 이해할 수 있도록 그림체가 명확히 다르기 때문에 위의 차트보다 접근성을 개선한 것을 확인할 수 있다. 이렇듯 그래프의 모양을 다르게 제공하여 그래프를 흑백처리해도 그래프 정보를 인식할 수 있는 등, 다양한 방법으로 컨텐츠에 접근할 수 있도록 해야한다.

<figure style="text-align:center">
  <figcaption>[ Link Sample ]</figcaption>
  <img src="./img/link-example.png" width="600">
</figure>

위 문장을 보면 **"미리보기 Cache 삭제하기"** 에 파란색으로 링크가 걸리 것을 확인할 수 있다. 이러한 형태의 링크 설명은 인터넷 사용을 하면서 흔히 볼 수 있을 것이다. 하지만 위의 차트 예시와 마찬가지로 색을 구분하지 못하는 저시력자, 시각 장애인은 해당 텍스트가 링크인지 아닌지 전혀 알 길이 없다. 따라서 저렇게 표현되기 보다는

<figure style="text-align:center">
  <figcaption>[ Link Sample (1) ]</figcaption>
  <img src="./img/link-button.png" width="400">
</figure>

위 예시와 같이 버튼을 확실하게 표현해주어 링크라는 것을 확실히 인식할 수 있도록 해주어야 한다. 즉, 지시사항은 모양, 크기, 위치, 방향, 색, 소리 등에 관계없이 인식될 수 있어야 한다

## Reference

- seulbinim github

  - https://seulbinim.github.io/WSA/embedded.html

- MDN

  - https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track
  - https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia

- W3C

  - https://www.w3.org/WAI/tutorials/images/complex/
  - https://www.w3.org/WAI/WCAG21/Understanding/audio-only-and-video-only-prerecorded.html
  - https://www.w3.org/WAI/WCAG21/Understanding/captions-prerecorded.html

- web seoul

  - http://www.websoul.co.kr/
