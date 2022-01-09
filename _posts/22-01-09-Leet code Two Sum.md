categories:
  -leetcode

배열의 숫자들을 잡게되어 타겟값이 되는경우 값이 나오는 함수 
단 같은 숫자는 두번 넣을수 없다 

가능한 모든 횟수를 시도하되 자기 자신은 2번이 나와서는 안되기 때문에 2번을 시작하지 않게 해야한다. 

그와 같은 값을 결과값으로 호출하는경우 다음과 같은 값이 나온다 


class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        
        a = {}
        
        
        for i, num in enumerate(nums):
            if target - num in a:
                return([a[target - num], i])
            elif num not in a:
                a[num] = i
