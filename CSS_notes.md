# CSS

## CSS의 정의 방법

### 인라인

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <h1 style="color: blue; font-size: 100px;">Hello</h1>
</body>
</html>
```



### 내부 참조

```html
!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    h1 {
      color: blue;
      font-size: 100px;
    }
  </style>
</head>
<body>
</body>
</html>
```



### 외부 참조

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link rel="stylesheet" href="mystyle.css">
</head>
<body>
  <h1>Hello</h1>
</body>
</html>
```

* 참조의 우선순위는 인라인 -> 외부, 내부 참조 -> 브라우저 디폴트값 순이다.



## CSS Properties

굉장히 다양한 요소들이 있기 때문에 필요할때 마다 찾아야 한다. 

[여기](#Resources) 에서 그때 그때 찾아보자 w3schools에서 제공하는 documentation이 개인적으로 가장 보기 좋았다.



### Color

```html
<!DOCTYPE html>
<html>
<body>
    <h2 style="background-color:Tomato;">Tomato</h1>
    <h2 style="background-color:Orange;">Orange</h1>
    <h2 style="background-color:rgb(255, 0, 0);">rgb(255, 0, 0)</h2>
    <h2 style="background-color:rgb(0, 0, 255);">rgb(0, 0, 255)</h2>
    <h2 style="background-color:#ffa500;">#ffa500</h2>
    <h2 style="background-color:#6a5acd;">#6a5acd</h2>
    <h2 style="background-color:hsl(39, 100%, 50%);">hsl(39, 100%, 50%)</h2>
	<h2 style="background-color:hsl(248, 53%, 58%);">hsl(248, 53%, 58%)</h2>
</body>
</html>
```

<!DOCTYPE html>
<html>
<body>
    <h2 style="background-color:Tomato;">Tomato</h1>
    <h2 style="background-color:Orange;">Orange</h1>
    <h2 style="background-color:rgb(255, 0, 0);">rgb(255, 0, 0)</h2>
    <h2 style="background-color:rgb(0, 0, 255);">rgb(0, 0, 255)</h2>
    <h2 style="background-color:#ffa500;">#ffa500</h2>
    <h2 style="background-color:#6a5acd;">#6a5acd</h2>
    <h2 style="background-color:hsl(39, 100%, 50%);">hsl(39, 100%, 50%)</h2>
	<h2 style="background-color:hsl(248, 53%, 58%);">hsl(248, 53%, 58%)</h2>
</body>
</html>



### Font Size

```html
<!DOCTYPE html>
<html>
<head>
<style>
h1 {
  font-size: 40px;
}

h2 {
  font-size: 30px;
}

p {
  font-size: 14px;
}
</style>
</head>
<body>

<h1>This is heading 1</h1>
<h2>This is heading 2</h2>
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>

</body>
</html>
```



### Font Family

```html
<!DOCTYPE html>
<html>
<head>
<style>
.p1 {
  font-family: "Times New Roman", Times, serif;
}

.p2 {
  font-family: Arial, Helvetica, sans-serif;
}

.p3 {
  font-family: "Lucida Console", "Courier New", monospace;
}
</style>
</head>
<body>

<h1>CSS font-family</h1>
<p class="p1">This is a paragraph, shown in the Times New Roman font.</p>
<p class="p2">This is a paragraph, shown in the Arial font.</p>
<p class="p3">This is a paragraph, shown in the Lucida Console font.</p>

</body>
</html>


```



### Margin

```html
<!DOCTYPE html>
<html>
<head>
<style>
div {
  margin: 70px;
  border: 1px solid #4CAF50;
}
</style>
</head>
<body>

<h2>CSS Margins</h2>

<div>This element has a margin of 70px.</div>

</body>
</html>
```



### Padding

```html
<!DOCTYPE html>
<html>
<head>
<style>
div {
  padding: 70px;
  border: 1px solid #4CAF50;
}
</style>
</head>
<body>

<h2>CSS Padding</h2>
<div>This element has a padding of 70px.</div>

</body>
</html>
```



## Resources

* [CSS Syntax (w3schools.com)](https://www.w3schools.com/css/css_syntax.asp)
* [CSS: Cascading Style Sheets | MDN (mozilla.org)](https://developer.mozilla.org/ko/docs/Web/CSS)