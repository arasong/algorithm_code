
```java
import java.io.;
import java.util.Stack;

public class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

        int n = Integer.parseInt(br.readLine());
        int count = 1;
        boolean err = false;

        StackInteger stack = new Stack();
        StringBuilder ret = new StringBuilder();

        for(int x=0;xn;x++) 데이터의 갯수만큼 반복한다.
        {
            int data = Integer.parseInt(br.readLine());
            while (count = data) 입력받은 data에 도달할 때까지 삽입
            {
                stack.push(count);
                count += 1;
                ret.append(+).append(n);
            }
            if(stack.peek() == data) 스택의 최상위 원소가 data와 같을 때 pop
            {
                stack.pop();
                ret.append(-).append(n);
            }
            else {
                err = true;
                break;
            }
        }
        if(err) System.out.println(NOn);
        else System.out.println(ret);  가능한 경우
    }
}
```
