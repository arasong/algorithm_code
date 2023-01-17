### 문제
스택:
https://www.acmicpc.net/problem/10828

### 소스
```javascript
// 직접 입력
const fs = require('fs');
const readFileSyncAddress = 'dev/stdin';

const input = fs.readFileSync(readFileSyncAddress).toString().trim().split('\n');
const inputLength = input.shift();

// 예시 변수 1
const inputLength = 14;
const input = [
'push 1', 'push 2', 'top', 'size', 'empty', 'pop', 'pop', 'pop',
'size', 'empty', 'pop', 'push 3', 'empty' ,'top'
];
// 예시 변수 2
const inputLength = 7;
const input = ['pop', 'top', 'push 123', 'top', 'pop', 'top', 'pop'];

let stack = [];
let result = [];
 
for (let i=0; i<inputLength; i++) {
	switch (input[i]) {
		case 'pop':
		// 스택에서 가장 위에 있는 정수를 빼고, 그 수를 출력. 
		// 스택에 들어있는 정수가 없는 경우에는 -1 출력
			result.push(stack[stack.length-1] || -1);
			stack.pop(stack[stack.length-1]);
		break;
		case 'size': // 스택에 들어있는 정수의 개수 출력
			result.push(stack.length);
		break;
		case 'empty': //  스택이 비어있으면 1, 아니면 0 출력
			result.push(stack[0] ? 0 : 1);
		break;
		case 'top': 
			// 스택의 가장 위에 있는 정수를 출력. 
			//스택에 들어있는 정수가 없는 경우에는 -1 출력
			result.push(stack[stack.length-1] || -1);
		break;
		default: // push: 정수 X를 스택에 넣는 연산
			stack.push(input[i].split(" ")[1]);
		break;
	}
}

console.log(result.join('\n'));
```