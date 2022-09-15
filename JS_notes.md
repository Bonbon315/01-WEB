# Javascript

## 주석

```javascript
// 한 줄 주석

/* 이건 더 긴,
 * 여러 줄 주석입니다.
 */

/* 그러나, /* 중첩된 주석은 쓸 수 없습니다 */ SyntaxError */
```

## 자료형

* var : **변수**를 선언. 추가로 동시에 값을 초기화.
* let : 블록 스코프 **지역 변수**를 선언. 추가로 동시에 값을 초기화.
* const : 블록 스코프 읽기 전용 **상수**를 선언.
  * 상수는 변수나 함수명과 동일한 이름으로 설정하면 에러가 발생한다

```javascript
if (true) {
  var x = 5;
}
console.log(x); // 5
```

```javascript
if (true) {
  let y = 5;
}
console.log(y); // ReferenceError: y is not defined
```

전역 변수와 지역 변수의 차이점

## 변수명

* JavaScript 식별자는 문자, 밑줄 (`_`) 혹은 달러 기호 (`$`)로 시작해야 함
* 대문자와 소문자를 구분함

## 조건문

if...else

```javascript
if (condition_1) {
  statement_1;
} else if (condition_2) {
  statement_2;
} else if (condition_n) {
  statement_n;
} else {
  statement_last;
}
```

switch

```javascript
switch (expression) {
  case label_1:
    statements_1;
    break;
  case label_2:
    statements_2;
    break;
    …
  default:
    statements_default;
}
```

try...catch

```javascript
function getMonthName(mo) {
  mo = mo - 1; // 배열 인덱스에 맞춰 월 조절 (1 = Jan, 12 = Dec)
  let months = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
  if (months[mo]) {
    return months[mo];
  } else {
    throw 'InvalidMonthNo'; // 여기서 throw 키워드 사용
  }
}

try {
  // 시도할 명령문
  monthName = getMonthName(myMonth); // 예외가 발생할 수 있는 함수
} catch (e) {
  monthName = 'unknown';
  logMyErrors(e); // 오류 처리기에 예외 객체 전달
}
```

`getMonthName()`은 매개변수의 값을 사용해 `months` 배열에서 영어 월 이름을 가져옵니다. 그런데 유효한 월(`1`-`12`) 범위의 숫자 값을 받은 것이 아니라면 `'InvalidMonthNo'`를 값으로 한 예외를 던집니다. 그러면 `catch` 블록의 명령문이 `monthName` 변수를 `'unknown'`으로 설정합니다.

## 반복문

for : c의 문법과 비슷함

```javascript
<form name="selectForm">
  <p>
    <label for="musicTypes">Choose some music types, then click the button below:</label>
    <select id="musicTypes" name="musicTypes" multiple="multiple">
      <option selected="selected">R&B</option>
      <option>Jazz</option>
      <option>Blues</option>
      <option>New Age</option>
      <option>Classical</option>
      <option>Opera</option>
    </select>
  </p>
  <p><input id="btn" type="button" value="How many are selected?" /></p>
</form>

<script>
function howMany(selectObject) {
  var numberSelected = 0;
  for (var i = 0; i < selectObject.options.length; i++) {
    if (selectObject.options[i].selected) {
      numberSelected++;
    }
  }
  return numberSelected;
}

var btn = document.getElementById("btn");
btn.addEventListener("click", function(){
  alert('Number of options selected: ' + howMany(document.selectForm.musicTypes))
});
</script>
```

do...while : 반드시 한번은 실행됨.

```javascript
do {
  i += 1;
  console.log(i);
} while (i < 5);
```

while

```javascript
n = 0;
x = 0;
while (n < 3) {
  n++;
  x += n;
}
```

break: 가장 가까운 반복문을 종료.

break [label]: 해당 레이블 종료

```javascript
var x = 0;
var z = 0
labelCancelLoops: while (true) {
  console.log("Outer loops: " + x);
  x += 1;
  z = 1;
  while (true) {
    console.log("Inner loops: " + z);
    z += 1;
    if (z === 10 && x === 10) {
      break labelCancelLoops;
    } else if (z === 10) {
      break;
    }
  }
}
```

continue, continue [label] 위와 같은 룰.

## 함수

파이썬과 크게 다를 바 없다

```javascript
function myFunc(theObject) {
  theObject.make = "Toyota";
}

var mycar = {make: "Honda", model: "Accord", year: 1998};
var x, y;

x = mycar.make; // x 의 값은 "Honda" 입니다.

myFunc(mycar);
y = mycar.make; // y 의 값은 "Toyota" 입니다.
                // (make 속성은 myFunc에서 변경되었습니다.)
```

### 내장함수

[`eval()`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/eval)

**`eval()`** 메소드는 문자열로 표현된 자바스크립트 코드를 수행합니다.

[`uneval()` (en-US)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Deprecated_and_obsolete_features) Non-standard

**`uneval()`** 메소드는 [`Object`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Object)의 소스코드를 표현하는 문자열을 만듭니다.

[`isFinite()`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/isFinite)

전역 **`isFinite()`** 함수는 전달받은 값이 유한한지 결정합니다. 만약 필요하다면, 매개변수는 첫번째로 숫자로 변환됩니다.

[`isNaN()`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/isNaN)

**`isNaN()`** 함수는 [`NaN`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/NaN)인지 아닌지 결정합니다. Note: `isNaN` 함수 안의 강제 변환은 [흥미로운](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isNaN#Description) 규칙을 가지고 있습니다; [`Number.isNaN()`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Number/isNaN)을 대신 사용하고 싶을것입니다, ECMAScript 6 에서 정의된,또는 값이 숫자값이 아닐때, [`typeof`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof) 를 사용할 수도 있습니다 .

[`parseFloat()`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/parseFloat)

**`parseFloat()`** 함수는 문자열 인수 값을 해석하여 부동소숫점 수를 반환합니다.

[`parseInt()`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/parseInt)

**`parseInt()`** 함수는 문자열 인수 값을 해석하여 특정한 진법의 정수를 반환합니다 (수학적 수 체계를 기반으로 해서).

[`decodeURI()`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/decodeURI)

**`decodeURI()`** 함수는 사전에 [`encodeURI`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/encodeURI)을 통해 만들어지거나 비슷한 과정을 통해 만들어진 URI(Uniform Resource Identifier) 를 해독합니다.

[`decodeURIComponent()`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/decodeURIComponent)

**`decodeURIComponent()`** 메소드는 사전에[`encodeURIComponent`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent)를 통하여 만들어 지거나 또는 비슷한 과정을 통해 만들어진 URI (Uniform Resource Identifier) 컴포넌트를 해독합니다.

[`encodeURI()`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/encodeURI)

**`encodeURI()`** 메소드는 URI(Uniform Resource Identifier)를 각 인스턴스의 특정한 문자를 한개, 두개,세개, 또는 네개의 UTF-8인코딩으로 나타내어지는 연속된 확장문자들과 바꾸는 방법으로 부호화 합니다 .(두"surrogate"문자로 구성된 문자들은 오직 네개의 연속된 확장문자 입니다. ).

[`encodeURIComponent()`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent)

**`encodeURIComponent()`** 메소드는 URI(Uniform Resource Identifier) 컴포넌트를 각 인스턴스의 특정한 문자를 한개, 두개,세개, 또는 네개의 UTF-8인코딩으로 나타내어지는 연속된 확장문자들과 바꾸는 방법으로 부호화 합니다 .(두"surrogate"문자로 구성된 문자들은 오직 네개의 연속된 확장문자 입니다. ).).

[`escape()` (en-US)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/escape) Deprecated

곧 사라질 **`escape()`** 메소드는 한 문자열에서 특정 문자들이 16진 확장 비트열로 바뀌어진 문자열로 계산합니다. [`encodeURI`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/encodeURI) 또는 [`encodeURIComponent`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent) 를 사용하세요.

[`unescape()` (en-US)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/unescape) Deprecated

곧 사라질 **`unescape()`** 메소드는 문자열에서 확장 비트열이 확장 비트열이 나타내는 문자로 바뀌어진 문자열로 계산합니다. [`escape` (en-US)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/escape)에서 확장 비트열이 소개될 것입니다. `unescape()` 메소드가 곧 사라지기 때문에, [`decodeURI()`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/decodeURI) or [`decodeURIComponent`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/decodeURIComponent) 를 대신 사용하세요.