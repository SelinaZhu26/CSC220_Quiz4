# CSC220_Quiz4

This solution solves the problem by reducing it to a classic subset sum (0/1 knapsack) problem. First, it computes the total sum of the array. If the sum is odd, it immediately returns false because two equal subsets cannot have an odd total. If the sum is even, the goal becomes determining whether there exists a subset whose sum equals half of the total sum.

The algorithm uses a one-dimensional dynamic programming array dp, where dp[j] represents whether a subset can achieve sum j. It initializes dp[0] = true since a sum of zero is always possible by choosing no elements. For each number in the array, it iterates backward from target down to the number, updating dp[j] to true if dp[j - num] was previously true. The backward iteration ensures each element is only used once, preserving the 0/1 constraint. If dp[target] becomes true at any point, the function can return early.

The time complexity is O(n × target), where n is the number of elements and target is half the total sum. Since target is at most sum/2, this is typically written as O(n × S) where S is the total sum. The space complexity is O(target) due to the one-dimensional DP array.
