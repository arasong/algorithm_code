class Solution {
    public int[] solution(int[] numbers) {
        int[] answer = new int[numbers.length];
        int n, m, result= 0;
        for (int i = 0; i < numbers.length; i++) {
            result =  -1;
            n = numbers[i];
            for (int j = i; j < numbers.length ; j++) {
                m = numbers[j];
                if(m > n){
                    result = m;
                    break;
                }
            }
            answer[i] = result;
        }        
        return answer;
    }
}
