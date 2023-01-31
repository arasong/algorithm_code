```java
package backjoon;

import java.util.Scanner;
import java.util.Stack;

public class Exam10773 {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        StringBuilder sb = new StringBuilder();

        int k = sc.nextInt();
        Stack<Integer> st = new Stack<>();
        int sum = 0;
        for(int i= 0; i<k; i++){
            int n = sc.nextInt();
            if(n==0 && st.size()>0){
                sum -= st.pop();
            }else{
                sum += n;
                st.push(n);
            }
        }

        System.out.println(sum);
    }
}
```