package bakjun;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.Stack;
import java.util.StringTokenizer;

/* 10828 */
public class test2 {
    public static Stack<Integer> stack = new Stack<>();
    public static void main(String[] args) throws IOException {
        BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
        StringBuilder sb = new StringBuilder();
        StringTokenizer st = null;
        int num = Integer.parseInt(bf.readLine());
        System.out.println(num);
        String str = "";
        for (int i = 0; i < num; i++) {
            st = new StringTokenizer(bf.readLine()); // 공백 단위로 데이터 읽기
            str = st.nextToken();
            if(str.indexOf("push") > -1){
                push(Integer.parseInt(st.nextToken()));
            } else if (str.indexOf("pop") > -1){
                sb.append(pop()).append("\n");
            } else if (str.indexOf("size") > -1){
                sb.append(size()).append("\n");
            } else if (str.indexOf("empty") > -1){
                sb.append(empty()).append("\n");
            } else if (str.indexOf("top") > -1){
                sb.append(top()).append("\n");
            }
        }
        System.out.println(sb);
    }

    // push X: 정수 X를 스택에 넣는 연산이다.
    public static void push (int val){
        stack.push(val);
    }

    // pop: 스택에서 가장 위에 있는 정수를 빼고, 그 수를 출력한다. 만약 스택에 들어있는 정수가 없는 경우에는 -1을 출력한다.
    public static int pop(){
        if(stack.isEmpty()){
            return -1;
        } else {
            return stack.pop();
        }

    }

    // size: 스택에 들어있는 정수의 개수를 출력한다.
    public static int size(){
        return stack.size();
    }

    // empty: 스택이 비어있으면 1, 아니면 0을 출력한다.
    public static int empty(){
        if(stack.isEmpty()){
            return 1;
        } else {
            return 0;
        }
    }

    // top: 스택의 가장 위에 있는 정수를 출력한다. 만약 스택에 들어있는 정수가 없는 경우에는 -1을 출력한다..
    public static int top(){
        if(stack.isEmpty()){
            return -1;
        } else {
            return stack.peek();
        }

    }
}
