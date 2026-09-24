# Tailwind CSS 연습

## 1. HTML 자동 완성 후 tailwind css cdn source script tag 삽입

### 1.1. ! 입력 후 tab 입력 으로 HTML 자동완성
```html
! 입력 후 tab 입력
```
### 1.2. <header> tag 에 `tailwind css cdn source script tag 삽입`
<script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>

```html
<!DOCTYPE html>
<html lang='ko'
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tailwind CSS</title>
  <!-- Tailwind CSS cdn source script tag 삽입 -->
  <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
</head>
<body>
    ......
</body>
</html>
```

## 2. Tailwind css snippet 으로 HTML 틀 자동완성

### 2.1. ctrl + shift + p > Snippets: Configure Snippets > html.json 선택
- tailwind-html snippet template 만들기

```json
{
	"Tailwind CDN Template": {
		"prefix": "tailwind-html",
		"body": [
			"<!DOCTYPE html>",
			"<html lang='ko'",
			"<head>",
			"  <meta charset=\"UTF-8\">",
			"  <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">",
			"  <title>$1</title>",
			"  <script src=\"https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4\"></script>",
			"</head>",
			"<body>",
			"    $1",
			"</body>",
			"</html>"
		],
		"description": "Basic HTML structure with Tailwind CSS CDN"
	}
}
```

### 2.2. Tailwind CSS HTML 자동완성 사용하기
- html 파일에서 html.json 에 정의한 prefix 입력

```html
tailwind-html

```

**➡️ snippet 사이트 사용 : `https://snippet-generator.app` 접속**
- 왼쪽 창에 snippet 템플릿화 할 소스 코드 붙혀넣기 
(javascript JSX, typescript, typescript JSX 소스 코드 틀)
- 오른 쪽 창에서 코드 내용 copy 해서
- vs code 에서 ctrl + shift + p
- Snippets: Configure Snippets
- javascriptreact, typescript, typescript JSX 선택해서 붙혀 넣기

## 3. VS Code 확장팩 설치

### 3-1. Tailwind CSS IntelliSense 설치
- Tailwind CSS 클래스 명을 입력 할때 자동완성 지원 기능

### 3-2. Tailwind CSS Intellisense 활성화

- workspace\tailwind.config.js 생성

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

### 3-3. prettier - Code formatter  확장팩 설치
- 에디터의 formatter 설정, 저장시 전체 파일의 포멧을 함

### 3-4. ctrl + , 로 Settings 의 설정 ( 사용자 / 작업영역: workspace\.vscode\setting.json )
- `Editor: Format on save` 를 `prettier - Code formatter` 로 설정
- `Editor: Format on save` 를 `체크`
- `Editor: Tab Size` 를 `2` 로 저장 ( 들여쓰기 2 칸 )
- workspace\.vscode\setting.json 확인

```json
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "editor.tabSize": 2
}
```

### 3-5. prettier 설정

```json
{
  "arrowParens": "always",                  // 화살표 함수에서 괄호를 항상 사용
  "bracketSpacing": true,                   // 객체 리터럴에서 중괄호와 속성사이에 공백 추가 
  "endOfLine": "auto",                      // 줄바꿈 스타일을 auto 로 설정
  "htmlWhitespaceSensitivity": "css",
  "jsxBracketSameLine": false,       
  "jsxSingleQuote": false,           
  "printWidth": 80,                         // 한줄에 80 자 까지 작성 
  "proseWrap": "preserve",           
  "quoteProps": "as-needed",          
  "semi": true,                             // 세미콜론 항상추가   
  "singleQuote": true,                      // 문자열에 홑 따옴표 사용
  "tabWidth": 2,                            // 텝 사이즈 2
  "trailingComma": "es5",                   // ES5 에서 유효한 곳에만 후행 콤마 추가
  "useTabs": false,                         // 탭 대신 스페이스 사용 
  "vueIndentScriptAndStyle": true,   
  "overrides": [ 
    {
      "files": "*.json",
      "options": {
        "printWidth": 200
      }
    }
  ]
}
```

---

## 4. Typograpy 스타일링

### 4.1. 글꼴크기(text-)
```html
text-2xl, text-sm, text-lg
```
### 4.2. 글꼴두께(font-) 
```html
font-bold, font-sm, font-lg
```
### 4.3. 텍스트정렬(text-)
```html
text-center, text-left, text-right
```
### 4.4. 텍스트색상(text-)
```html
text-red-500, text-blue-500, text-green-500
```
### 4.5. 줄 간격(leading-)
```html
leading-none, leading-tight, leading-relaxed
```
### 4.6. 텍스트 오버플로우(text-)
```html
text-ellipsis, text-clip, text-nowrap
```

---

## 5. 