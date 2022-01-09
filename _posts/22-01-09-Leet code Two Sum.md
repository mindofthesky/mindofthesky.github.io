답 

해설 추후 작성 


class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        
        a = {}
        
        
        for i, num in enumerate(nums):
            if target - num in a:
                return([a[target - num], i])
            elif num not in a:
                a[num] = i
