### 문제
스택 수열 :
https://www.acmicpc.net/problem/1874

### 소스
```javascript
// 입력받기 위해 사용 -> 자바스크립트 file system
const fs = require('fs');
const readFileSyncAddress = 'dev/stdin';
const input = fs.readFileSync(readFileSyncAddress).toString().trim().split('\n');
const inputLength = input.shift();

// 예시 변수
const inputLength = 8;
const input = [4,3,6,8,7,5,2,1]; 

const result = []; // 결과 배열
const stack = []; // 스택 변수

let stackNum = 1; // 스택을 1부터 순서대로 넣기 위해 1로 시작
let num;

for (let i=0; i< inputLength ; i++) {
	num = input[i];

	// stackNum은 1부터 num까지 증가
	// push할 때마다 result 배열에 '+' push 해줌
	while (stackNum <= num) {
		stack.push(stackNum);
		stackNum++;
		result.push('+');
	}

	// stack에 num까지 들어갔다면, pop 해줌
	// pop할 때마다 result 배열에 '-' push 해줌
	let stackPop = stack.pop();
	result.push('-');

	// stack에 pop한 값과 num이 일치하지 않으면 NO를 출력하며 for문 강제 종료
	if (stackPop !== num) {
		result = ['NO'];
		break;
	}
}

console.log(result.join('\n'));
```

