package bakjun;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.Arrays;
import java.util.StringTokenizer;

/* 1920 */
public class Test6 {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        StringBuilder sb = new StringBuilder();

        // n
        int n = Integer.parseInt(br.readLine());
        int[] arr = new int[n];
        StringTokenizer st = new StringTokenizer(br.readLine());
        for (int i = 0; i < n ; i++) {
            arr[i] = Integer.parseInt(st.nextToken());
        }

        Arrays.sort(arr); // 받은수 정렬

        // m
        n = Integer.parseInt(br.readLine());
        st = new StringTokenizer(br.readLine());
        int num = 0;
        for (int i = 0; i < n ; i++) {
            num = Integer.parseInt(st.nextToken());
            if (Arrays.binarySearch(arr, num) >= 0) { // 배열과 숫자를 비교하여 찾으면 해당 index 반환, 못찾음 -반환
                sb.append(1).append("\n");
            } else {
                sb.append(0).append("\n");
            }
        }
        System.out.println(sb);

    }
}
