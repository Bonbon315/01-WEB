# HTML

## 기본 구조

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My test page</title>
  </head>
  <body>
    <p>This is my page</p>
  </body>
</html>

```



## 핵심 태그

### 텍스트 요소

| **태그**                             | **설명**                                                     |
| :----------------------------------- | ------------------------------------------------------------ |
| `<a> </a>`                           | href 속성을 활용하여 다른 URL로 연결하는 하이퍼링크 생성     |
| `<b> </b>`<br />`<strong> </strong>` | 굵은 글씨 요소<br />중요한 강조하고자 하는 요소              |
| `<i> </i>`<br />`<em> </em>`         | 기울임 글씨 요소<br />중요한 강조하고자 하는 요소            |
| `<br>`                               | 텍스트 내에 줄 바꿈 생성                                     |
| `<img>`                              | src 속성을 활용하여 이미지 표현,<br />alt 속성을 활용하여 대체 텍스트 |
| `<span> </span>`                     | 의미 없는 인라인 컨테이너                                    |
| `<h1> </h1>`                         | heading.                                                     |

### 그룹 컨텐츠

| **태그**                            | **설명**                                                     |
| ----------------------------------- | ------------------------------------------------------------ |
| `<p> </p>`                          | 하나의 문단 (paragraph)                                      |
| `<hr>`                              | 문단 레벨 요소에서의 주제의 분리를 의미하며 수평선으로 표현됨<br />-------------------------------------------------------------------------------------------------- |
| `<ol> </ol>`<br />`<ul> </ul>`      | Ordered list<br />Unordered list                             |
| `<pre> </pre>`                      | HTML에 작성한 내용을 그대로 표현.<br />보통 고정폭 글꼴이 사용되고 공백 문자를 유지 |
| `<blockquote>`<br />`</blockquote>` | 텍스트가 긴 인용문<br />주로 들여쓰기를 한 것으로 표현됨     |
| `<div> </div>`                      | 의미 없는 블록 레벨 컨테이너                                 |



## HTML에서 일부 특수문자 출력하기

| Name | Character | Unicode code point (decimal) | Standard |                             Name                             |
| :--: | :-------: | :--------------------------: | :------: | :----------------------------------------------------------: |
| quot |     "     |         U+0022 (34)          | XML 1.0  | [quotation mark](https://en.wikipedia.org/wiki/Quotation_mark) |
| amp  |     &     |         U+0026 (38)          | XML 1.0  |     [ampersand](https://en.wikipedia.org/wiki/Ampersand)     |
| apos |     '     |         U+0027 (39)          | XML 1.0  | [apostrophe](https://en.wikipedia.org/wiki/Apostrophe) (1.0: apostrophe-quote) |
|  lt  |     <     |         U+003C (60)          | XML 1.0  | [less-than sign](https://en.wikipedia.org/wiki/Less-than_sign) |
|  gt  |     >     |         U+003E (62)          | XML 1.0  | [greater-than sign](https://en.wikipedia.org/wiki/Greater-than_sign) |

* [List of XML and HTML character entity references - Wikipedia](https://en.wikipedia.org/wiki/List_of_XML_and_HTML_character_entity_references)
* `&amp;` 이렇게 쓰면 페이지엔 &amp; 이 노출된다



## Head

```html
<head>
  <meta charset="utf-8">
  <link rel="stylesheet" href="my-css-file.css">
  <script src="my-js-file.js"></script>
  <title>My test page</title>
</head>
```

* `<title>` 엔 웹페이지 제목이 들어간다. 인터넷 탭 이름에 노출되는 그것.
* `<meta>` 엔 각종 요소들이 들어간다. charset을 지정하거나, 네이버의 다크모드등이 여기서 정의 될 수 있다.
* `<link>` 로 css파일을 연결 할 수 있다.
  * css 파일은 디자인 요소를 담당한다.
* `<script>`로 javascript파일을 지정할 수 있다.
  * javascript는 웹페이지에 텍스트나 이미지 이외의 많은 요소들을 구현하기 위해 사용된다.



## Hyperlink

```html
<p>I'm creating a link to
<a href="https://www.mozilla.org/en-US/"
   title="The best place to find more information about Mozilla's
          mission and how to contribute">the Mozilla homepage
</a>.
<a href="https://download.mozilla.org/?product=firefox-39.0-SSL&os=win&lang=en-US"
   download="firefox-39-installer.exe">
  Download Firefox 39 for Windows
</a>    
</p>
```

* `href` 를 통해 링크 제공.
  * 이때, 같은 디렉토리 안의 파일이나 하위폴더의 파일로 링크를 하려면, `<a href="contacts.html">` / `<a href="projects/index.html">` 의 방식으로 표현 할 수 있다.
* `title`에 포함되는 내용은 마우스 호버시에 보이는 내용이다.
* `download` 요소를 통해 기본 저장 파일 이름을 제공 할 수 있다.



## Image

```htm
<img src="images/dinosaur.jpg">
<img src="https://www.example.com/images/dinosaur.jpg">
<img src="images/dinosaur.jpg"
     alt="The head and torso of a dinosaur skeleton;
          it has a large head with long sharp teeth"
     width="400"
     height="341">
```

* 상대경로나 절대경로를 통해 이미지를 link한다
* `alt` 요소를 통해 이미지가 보이지 않을 경우 설명문으로 대체할 수 있다
* `width` `height` 요소로 이미지의 크기를 조정할 수 있다



## Video

```html
<video controls>
  <source src="rabbit320.mp4" type="video/mp4">
  <source src="rabbit320.webm" type="video/webm">
  <p>Your browser doesn't support HTML5 video. Here is a <a href="rabbit320.mp4">link to the video</a> instead.</p>
</video>
```

<video controls>
  <source src="rabbit320.mp4" type="video/mp4">
  <source src="rabbit320.webm" type="video/webm">
  <p>Your browser doesn't support HTML5 video. Here is a <a href="rabbit320.mp4">link to the video</a> instead.</p>
</video>



## Table

```html
<table>
  <tr>
    <td>&nbsp;</td>
    <td>Knocky</td>
    <td>Flor</td>
    <td>Ella</td>
    <td>Juan</td>
  </tr>
  <tr>
    <td>Breed</td>
    <td>Jack Russell</td>
    <td>Poodle</td>
    <td>Streetdog</td>
    <td>Cocker Spaniel</td>
  </tr>
  <tr>
    <td>Age</td>
    <td>16</td>
    <td>9</td>
    <td>10</td>
    <td>5</td>
  </tr>
  <tr>
    <td>Owner</td>
    <td>Mother-in-law</td>
    <td>Me</td>
    <td>Me</td>
    <td>Sister-in-law</td>
  </tr>
  <tr>
    <td>Eating Habits</td>
    <td>Eats everyone's leftovers</td>
    <td>Nibbles at food</td>
    <td>Hearty eater</td>
    <td>Will eat till he explodes</td>
  </tr>
</table>
```

<table>
  <tr>
    <td>&nbsp;</td>
    <td>Knocky</td>
    <td>Flor</td>
    <td>Ella</td>
    <td>Juan</td>
  </tr>
  <tr>
    <td>Breed</td>
    <td>Jack Russell</td>
    <td>Poodle</td>
    <td>Streetdog</td>
    <td>Cocker Spaniel</td>
  </tr>
  <tr>
    <td>Age</td>
    <td>16</td>
    <td>9</td>
    <td>10</td>
    <td>5</td>
  </tr>
  <tr>
    <td>Owner</td>
    <td>Mother-in-law</td>
    <td>Me</td>
    <td>Me</td>
    <td>Sister-in-law</td>
  </tr>
  <tr>
    <td>Eating Habits</td>
    <td>Eats everyone's leftovers</td>
    <td>Nibbles at food</td>
    <td>Hearty eater</td>
    <td>Will eat till he explodes</td>
  </tr>
</table>

* `<tr>` 요소로 행
* `<td>` 요소로 열



## Resources

* [HTML 요소 참고서 - HTML: Hypertext Markup Language | MDN (mozilla.org)](https://developer.mozilla.org/ko/docs/Web/HTML/Element)
* [PowerPoint 프레젠테이션 (amazonaws.com)](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/2857a1d5-7b30-4e0c-be48-3adeec38f4bc/web_01.pdf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220829%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220829T043817Z&X-Amz-Expires=86400&X-Amz-Signature=4a686ca7ea1dc0397c2bb27a8cb79ed7f961fa3368fcf489a0624b1f3613af24&X-Amz-SignedHeaders=host&response-content-disposition=filename %3D"web_01.pdf"&x-id=GetObject)

