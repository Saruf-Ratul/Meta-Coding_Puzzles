from typing import List
# Write any import statements here

def getMaximumEatenDishCount(N: int, D: List[int], K: int) -> int:
  # Write your code here
   res = list(set(D[:K]))
  for i in range(K, len(D)):
    slice = res
    if len(res) > K:
      slice = res[-K:]
    if D[i] not in slice:
      res.append(D[i])

  return len(res)
print(getMaximumEatenDishCount(6, [1, 2, 3, 3, 2, 1], 1))
print(getMaximumEatenDishCount(6, [1, 2, 3, 3, 2, 1], 2))
print(getMaximumEatenDishCount(7, [1, 2, 1, 2, 1, 2, 1], 2))