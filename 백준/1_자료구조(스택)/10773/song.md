1. 스택(stack) 자료구조를 구현 할 수 있다면 쉽게 풀 수 있다.
2. 입력으로 0이 들어오는 경우 가장 최근에 입력된 원소를 제거
3. 이는 스택(stack)의 pop() 함수와 동일한 기능으로 이해할 수 있다.
<br>

```java

import java.io.*;
import java.util.*;

public class Main {

    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        StringBuilder sb = new StringBuilder();
        StringTokenizer st;

        int K;
        int sum = 0;

        K = Integer.parseInt(br.readLine()); //명령의 수 입력

        ArrayList stack = new ArrayList();
        for(int x=0;x<K;x++)
        {
            int n = Integer.parseInt(br.readLine());
            if(n != 0 )
            {
                stack.add(n);
                sum+=n;
            } else if (n == 0 ){ //값이 0인 경우 가장 최근 수 제거
                sum -= (int)stack.get(stack.size()-1);
                stack.remove(stack.size()-1);
            }
        }
        System.out.println(sum);
    }

}


```
