### 문제
제로: https://www.acmicpc.net/problem/10773

### 소스
```javascript
const fs = require('fs');
const readFileSyncAddress = 'dev/stdin';

const input = fs.readFileSync(readFilesSyncAddress).toString().trim().split('\n');
const inputLength = input.shift();

// 예시 입력1
const inputLength = 4;
const input = [3,0,4,0];

// 예시 입력2
const inputLength = 10;
const input = [1,3,5,4,0,0,7,0,0,6];

const stack = [];

for (let i=0; i<inputLength; i++) {
  if (input[i] === 0 && input[i]-1) {
    stack.pop();
  }else {
    stack.push(input[i]);
  }
}

let result = stack.length ? stack.reduce((acc, item) => acc + item, 0) : 0;

console.log(result);
```