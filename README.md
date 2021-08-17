## 프로젝트 생성

### <u>package.json</u> 파일 생성
```
npm init -y
```

### parcel-bundler 설치
```
npm i -D parcel-bundler
```

### <u>package.json</u> 파일에 <u>scripts</u> 부분 변경
```javascript
  "scripts": {
    "dev": "parcel index.html",
    "build": "parcel build index.html"
  },
```
### scss 추가
```html
  <link rel="stylesheet" href="./scss/main.scss">
```

### javascript 추가
```html
<script defer src="./js/main.js"></script>
```
### reset.css cdn 추가

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reset-css@5.0.1/reset.min.css">
```

### favicon 파일 만들기
`파비콘 만들기` : https://www.icoconverter.com/

### 정적 파일 연결
`정적파일연결` : https://www.npmjs.com/package/parcel-plugin-static-files-copy 
```bash
npm install -D parcel-plugin-static-files-copy
```

#### <u>package.json</u> 파일변경
```json
"staticFiles": {
    "staticPath": "static"
}
```

### postcss autoprefixer 설치
```bash
npm i -D postcss autoprefixer
```
#### <u>package.json</u> 파일변경
```json
  "browserslist": [
    ">1%",
    "last 2 versions"
  ]
```

### .postcssrc.js 작성
```javascript
//import
const autoprefixer = require('autoprefixer')

// export
module.exports = {
  plugins: [
    autoprefixer
  ]
}
```

### Error: PostCSS plugin autoprefixer requires PostCSS 8.
- autoprefixer 10버전에서 8버전으로 다운그레이드
https://stackoverflow.com/questions/64057023/error-postcss-plugin-autoprefixer-requires-postcss-8-update-postcss-or-downgra
```bash
npm i -D autoprefixer@9
```


## Babel
https://en.wikipedia.org/wiki/Babel_(transcompiler)

- ES6, ES7, ES8 을 ES5로 변환(compile)
```bash
npm i -D @babel/core @babel/preset-env
```
### .babelrc.js 파일 생성
```javascript
module.exports = {
  presets:['@babel/preset-env']
}
```

### Promise 객체 적용 안되는 문제 해결
```bash
npm i -D @babel/plugin-transform-runtime
```
#### .babelrc.js 플러그인 추가
```javascript
module.exports = {
  presets:['@babel/preset-env'],
  plugins:[
    ['@babel/plugin-transform-runtime']
  ]
}
```

## github 관리
```git
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/Chang-ji/Parcel-example.git
git push -u origin main
```
