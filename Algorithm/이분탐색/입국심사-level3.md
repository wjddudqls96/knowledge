# 수 찾기 - 실버 4

* 문제 
    ```
    n명이 입국심사를 위해 줄을 서서 기다리고 있습니다. 각 입국심사대에 있는 심사관마다 심사하는데 걸리는 시간은 다릅니다.

    처음에 모든 심사대는 비어있습니다. 한 심사대에서는 동시에 한 명만 심사를 할 수 있습니다. 가장 앞에 서 있는 사람은 비어 있는 심사대로 가서 심사를 받을 수 있습니다. 하지만 더 빨리 끝나는 심사대가 있으면 기다렸다가 그곳으로 가서 심사를 받을 수도 있습니다.

    모든 사람이 심사를 받는데 걸리는 시간을 최소로 하고 싶습니다.

    입국심사를 기다리는 사람 수 n, 각 심사관이 한 명을 심사하는데 걸리는 시간이 담긴 배열 times가 매개변수로 주어질 때, 모든 사람이 심사를 받는데 걸리는 시간의 최솟값을 return 하도록 solution 함수를 작성해주세요.

* 제한사항
    * 입국심사를 기다리는 사람은 1명 이상 1,000,000,000명 이하입니다.

    * 각 심사관이 한 명을 심사하는데 걸리는 시간은 1분 이상 1,000,000,000분 이하입니다.

    * 심사관은 1명 이상 100,000명 이하입니다.

* 입출력 예
    * ![스크린샷 2023-09-03 오후 4 59 08](https://github.com/wjddudqls96/java/assets/59672589/9d87553f-1097-4817-a69f-877e9eb377b4)


## 풀이방법

* 심사관은 시간만큼 각각의 손님을 받는다

* mid / times[i] 을 통해 sum 을 구한다. -> 총 처리할 수 있는 손님 수

* 이분 탐색을 통해서 처리해야될 사람보다 sum이 작다면 mid를 높힌다.

* 처리해야될 사람보다 sum 크다면 mid를 줄인다.

``` java
import java.util.*;

class Solution {
    public long solution(int n, int[] times) {
        long answer = 0;
        Arrays.sort(times);
        
        long min = 0;
        long max = (long) n * times[times.length - 1];
        
        while(min <= max){
            long mid = (min + max) / 2;
            long sum = 0;
            
            for(int i = 0; i < times.length; i++){
                sum += mid / times[i];
            }
            
            if(sum < n){ // 처리해야될 사람보다 처리를 못했다면 mid를 높힌다.
                min = mid + 1;
            }
            else {
                max = mid - 1;
                answer = mid;
            }
        }
        
        return answer;
    }
}
```

![스크린샷 2023-09-03 오후 5 03 41](https://github.com/wjddudqls96/java/assets/59672589/2cebe288-82b9-499d-beda-193675cbff01)