import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.Stack;
import java.util.StringTokenizer;


public class Main {
    public static void main(String[] args) throws IOException {

        BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
        StringBuilder sb = new StringBuilder();

        int index = Integer.parseInt(bf.readLine());
        int[] tmpList = new int[index] ;
        StringTokenizer st = new StringTokenizer(bf.readLine()); // 공백 단위로 데이터 읽기
        for (int i = 0; i < index; i++) tmpList[i] = Integer.parseInt(st.nextToken()); // 입력데이터 넣기

        Stack stack = new Stack(); // 결과 stack
        boolean pushYN = false; // stack에  push 체크여부
        for (int i = 0; i < index; i++) {
            pushYN = false;
            for (int j = i; j < tmpList.length; j++) {
                if(tmpList[i] < tmpList[j]){
                    stack.push(tmpList[j]);
                    pushYN = true;
                    break;
                }
            }
            if(!pushYN) stack.push(-1); // 만일 오른쪽 큰수를 못찾았다면 -1 push
        }

        for (Object object : stack) {
            sb.append(object.toString() + " ");
        }

        System.out.println(sb); // 결과 출력
    }
}
