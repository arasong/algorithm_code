package bakjun;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.Stack;
import java.util.StringTokenizer;

/* 10773 */
public class test3 {
    public static Stack<Integer> stack = new Stack<>();
    public static void main(String[] args) throws IOException {
        BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
        StringBuilder sb = new StringBuilder();
        int index = Integer.parseInt(bf.readLine());

        int num = 0;
        for (int i = 0; i < index; i++) {
            num = Integer.parseInt(bf.readLine());
            if (num == 0) {
                stack.pop(); // 0일경우 가장 최근에 쓴 수를 지움
            } else {
                stack.push(num); // 아니면 stack에 push
            }
        }
        
        // 모든수를 받아적은후 수의 합
        int sum = 0;
        for (int n: stack) {
            sum += n;
        }
        System.out.println(sum);
    }
}
