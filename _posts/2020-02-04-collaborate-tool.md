---
title: "[TID] 협업을 위한 툴"
date: 2020-02-04 22:35:00 -0400
categories: TID collaborate tool jest eslint
---
사람들과 협업을 하다보면 코드 가독성, 디버그, 등등 많은 불편함에 마주한다. 그러한 불편함을 줄여주기 위한 tool 이 있어 소개를 한다.
## [jest](https://jestjs.io/)
jest 는 unit 단위의 코드 test 를 위한 tool 이다.
### 사용법
```js
// math.js

function add(x, y) {
  return x + y;
}

export default add;
```

```js
const add = require('../math');
 
test('add 1 + 2 to equal 3', () => {
  expect(add(1, 2)).toBe(3);
});
```

## [eslint](https://eslint.org/)
eslint 는 서로 다른 사람이 collaborate 를 하며, 코드 가독성을 높히기 위한 규칙을 정하는 것이다. <br/>
1. editor extensions 을 통해 eslint 를 설치한후
2. npm 을 이용해 eslint 를 설치
3. eslint init 을 통해 .eslintrc.json 파일을 설치한다
4. 이후 extends, env, rules 을 설정한다
```js
{
  "extends": "airbnb",
  "env": {
    "node": true,
    "es6": true,
    "jest": true
  },
  "rules": {}
}
```

### 느낀점
jest, eslint, git 을 배우기전 협업은 슬랙을 이용해서 코드를 복사 붙히기, 어려운 가독성, 찾기힘든 버그 로 
인해 코드 작성시간보다 merge 에 더 많은 시간을 투자했다면 이번 기회를 통해 코드작성 에 좀더 힘을 쓸수 있는 협업이 되었다.

### 부족한점
- 여전히 내 생각을 페어분께 완벽하게 전달하기에는 힘이 들었다.
- 용어를 배워 좀더 간략하게 설명할수 있는 방법을 배워야겠다.
- method 의 쓰임새를 좀더 정확히 알아 허비하는 시간을 줄여야 겟다.
