categories:
  -leetcode

배열의 숫자들을 잡게되어 타겟값이 되는경우 값이 나오는 함수 
단 같은 숫자는 두번 넣을수 없다 

가능한 모든 횟수를 시도하되 자기 자신은 2번이 나와서는 안되기 때문에 2번을 시작하지 않게 해야한다. 

그와 같은 값을 결과값으로 호출하는경우 다음과 같은 값이 나온다 

파이썬의 기초적인 특징을 짚고 넘어 가야한다

파이썬에는 for, foreach 같은 다른 반복문을 지원하지 않는다. 단 하나의 for과 변수 
즉 for i, in range(n) 과 함께 진행이되며 이를 통한 이중포문 3중포문을 작성하게된다 

enumerate 함수는 리스트를 데이터형을 받은경우 리스트의 값을 전달하여 값을 보냅니다 

이를 통한 두수를 더해서 값을 맞는 값을 판별하는 알고리즘을 작성하게됩니다. 


class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        
        a = {}
        
        
        for i, num in enumerate(nums):
            if target - num in a:
                return([a[target - num], i])
            elif num not in a:
                a[num] = i
