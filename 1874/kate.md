package sample;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.Scanner;
import java.util.Stack;

public class test1 {
    public static void main(String[] args) throws IOException {
        BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
        int num = Integer.parseInt(bf.readLine());
        Stack<Integer> stack = new Stack<>();
        int finalVal = 0;
        int val = 0;
        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < num; i++) {
            val = Integer.parseInt(bf.readLine());
            if(val > finalVal){
                for (int j = finalVal +1 ; j <= val ; j++) {
                    System.out.println(val + "/" + j);
                    stack.push(j);
                    sb.append("+").append("\n");
                }
                finalVal = val;
            } else {
                if(stack.peek() != val){
                    System.out.println("NO");
                    return;
                }
            }
            stack.pop();
            sb.append("-").append("\n");
        }
        System.out.println(sb);
    }
}
