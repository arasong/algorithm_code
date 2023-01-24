-- https://www.acmicpc.net/problem/1874

```java
import java.util.ArrayList;
import java.util.Scanner;
import java.util.Stack;

public class exam1874{

	public static void main(String[] args) {
    // 문제입력
		Scanner sc = new Scanner(System.in);
		Stack st = new Stack();
		ArrayList ans = new ArrayList();
		int n = sc.nextInt();
		int[] inputArr = new int[n + 1];
		int m = 1;
		for (int i = 1; i <= n; i++) {
			inputArr[i] = sc.nextInt();
		}

		for (int i = 1; i <= n; i++) {
			st.push(i);
			ans.add("+");
			while (!st.empty() && st.peek() == inputArr[m]) {
				st.pop();
				ans.add("-");
				m++;
			}
		}

		if (st.empty()) {
			for (String s : ans) {
				System.out.println(s);
			}
		} else {
			System.out.println("NO");
		}

	}
}


```
