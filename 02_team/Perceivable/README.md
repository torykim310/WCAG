# Perceivalbe

## 1. Text Alternatives

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

또 다른 예시로, 동영상의 경우에는 시각 장애인과 청각 장애인 모두에게 접근성이 떨어진다. 따라서 오디오나 동영상의 경우에는 `track` 태그를 통해서 자막(텍스트)을 제공해주어야 한다.

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

이러한 방식으로 대체 텍스트를 제공해주어 `non-text content`에 대한 접근성을 확보해줄 수 있다.

## 2. Time-based Media

> Provide alternatives for time-based media.

## 3. Adaptable

> Create content that can be presented in different ways (for example simpler layout) without losing information or structure

## 4. Distinguishable

> Make it easier for users to see and hear content including separating foreground from background.

## Reference

- MDN

  - https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track
  - https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia

- W3C
  - https://www.w3.org/WAI/tutorials/images/complex/
