```java
import java.util.Scanner;
import java.util.Stack;

public class exam10828 {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        StringBuilder sb = new StringBuilder();
        int n = sc.nextInt();
        Stack st = new Stack();

        for (int i = 0; i <= n; i++) {
            String inputString = sc.nextLine();
            String[] s = inputString.split(" ");
            switch (s[0]){
                case "push" :
                    st.push(s[1]);
                    break;
                case "pop" :
                    sb.append(st.empty()?-1:st.pop()).append('\n'); break;
                case "size" :
                    sb.append(st.size()).append('\n'); break;
                case "empty" :
                    sb.append(st.empty()?1:0).append('\n'); break;
                case "top" :
                    sb.append(st.size()>0?st.peek():-1).append('\n'); break;
            }
        }
        System.out.println(sb);

    }
}



```