## 완전 검색

- 완전 검색 방법은 문제의 해법으로 생각할 수 있는 모든 경우의 수를 나열해보고 확인하는 기법이다.
- Brute-force 혹은 generate-and-test 기법이라고 불리운다. → 고지식한 방법
- 모든 경우의 수를 테스트한 후, 최종 해법을 도출한다.
- 상대적으로 빠른 시간에 문제 해결을 할 수 있다.
- 일반적으로 경우의 수가 상대적으로 작을 때 유용하다.

## 완전 검색을 활용한 Baby-gin 접근

- 6개의 숫자로 만들 수 있는 모든 숫자 나열(중복 포함)
- 예) 입력으로 `{2, 3, 5, 7, 7, 7}`을 받았을 경우, 아래와 같이 순열을 생성할 수 있다.
    
    <img src="https://file.notion.so/f/s/0510e504-2534-4b77-a771-b6a5769a5154/Untitled.png?id=a82440d5-cff7-40b9-874f-51f7e941b92f&table=block&spaceId=e115423d-0a97-4b37-9fff-0ad5ef1d11e7&expirationTimestamp=1693836000000&signature=08hX6MMts8fy65xF4fbV_ZlhbduP9BI05tNENwH1j08&downloadName=Untitled.png"/>
    
- 해답 테스트하기
    - 앞의 3자리와 뒤의 3자리를 잘라, run와 triplet 여부를 테스트하고 최종적으로 baby-gin을 판단한다.
        
        <img src="https://file.notion.so/f/s/1c01d5d3-1dd6-4d9d-8dda-3091e760896e/Untitled.png?id=131e1ebf-9c9d-49d8-86b8-742e17bb8c34&table=block&spaceId=e115423d-0a97-4b37-9fff-0ad5ef1d11e7&expirationTimestamp=1693836000000&signature=-bTecsRo6VqwwF6lKe8830IvGSlHrvzvff405wZdFZ0&downloadName=Untitled.png"/>
        

## 조합적 문제

<img src="https://file.notion.so/f/s/0d35ee0e-e1a6-44c4-aec9-32da4e00f221/Untitled.png?id=d278a7f4-5345-4b74-a114-f3ad46994a26&table=block&spaceId=e115423d-0a97-4b37-9fff-0ad5ef1d11e7&expirationTimestamp=1693836000000&signature=n9NLgn9VsExpfbBdlCzqEe497oOuYcaNlhtM1AkoIQQ&downloadName=Untitled.png"/>

## 완전 검색

- 많은 종류의 문제들이 특정 조건을 만족하는 경우나 요소를 찾는 것이다.
- 또한 이들은 전형적으로 `순열(Permutation)`, `조합(Combination)`, 그리고 `부분집합(subset)`과 같은 **조합적 문제들(Combinatorial Problems)** 과 연관된다.

### 순열(Permutation)

- 서로 다른 것들 중 몇 개를 뽑아서 한 줄로 나열하는 것
- 서로 다른 n개 중에서 r개를 택하는 순열은 아래와 같이 표현한다.
    
    **nPr**
    
- 그리고 nPr은 다음과 같은 식이 성립한다.
    
    **nPr = n * (n - 1) * (n - 2)* ….. * (n-r+1)**
    
- nPn = n! 이라고 표기하며 Factorial이라 부른다.
    
    **nPn = n * (n - 1) * (n - 2)* ….. * 1**
    
- N 개의 요소들에 대해서 n! 개의 순열들이 존재한다.
    - 12! = 479,001,600
    - **n > 12 인 경우, 시간 복잡도 폭발적으로 증가한다!**
    
    <img src="https://file.notion.so/f/s/f4801e77-7af8-4381-979d-f81cb6a3ddda/Untitled.png?id=574a6043-bd00-441a-a4a9-1423c0d5bda4&table=block&spaceId=e115423d-0a97-4b37-9fff-0ad5ef1d11e7&expirationTimestamp=1693836000000&signature=OwS1KIypssUUWJun63GAdH9NUKeTrSDAg010JwbEhuM&downloadName=Untitled.png"/>
    