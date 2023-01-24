```java
import java.io.*;
import java.util.StringTokenizer;

public class Main {
    public static int stack[];
    public static int size = 0;

    public static void push (int x){
        //정수 X를 스택에 넣는 연산이다.
        stack[size] = x;
        size++;
    }

    public static int pop (){
        //스택에서 가장 위에 있는 정수를 빼고, 그 수를 출력
        //스택에 들어있는 정수가 없는 경우에는 -1을 출력
        if(size == 0 ){
            return -1;
        }
      else{
            int ret = stack[size-1];
            stack[size-1]=0;
            size--;
            return ret;
        }
    }

    public static int size (){
        //스택에 들어있는 정수의 개수를 출력
        return size;
    }

    public static int empty (){
        //스택이 비어있으면 1, 아니면 0을 출력
        if(size == 0) return 1;
        else return 0;
    }

    public static int top (){
        //스택의 가장 위에 있는 정수를 출력,정수가 없는 경우에는 -1을 출력
        if(size == 0) return -1;
        else return stack[size-1];
    }

    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        StringBuilder sb = new StringBuilder();
        StringTokenizer st;
        int N;
        int result;
        N = Integer.parseInt(br.readLine()); //명령의 수 입력
        stack  = new int[N]; // 스택 초기화
        for(int x=0;x<N;x++)
        {
            st = new StringTokenizer(br.readLine(), " "); //공백 기준 구분
            switch (st.nextToken()){
                case "push" : //원소삽입
                    push(Integer.parseInt(st.nextToken()));
                    break;
                case "pop" : //원소삭제
                    result = pop();
                    sb.append(result).append("\n");
                    break;
                case "size" : //원소의 개수 출력
                    result = size();
                    sb.append(result).append("\n");
                    break;
                case "empty" : //스택이 비어있는지 출력
                    result = empty();
                    sb.append(result).append("\n");
                    break;
                case "top" : //최상단 원소 출력
                    result = top();
                    sb.append(result).append("\n");
                    break;
            }
        }

        System.out.println(sb);
    }

}
