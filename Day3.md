# Problem 1: Second Largest and Second Smallest in an Array

## Link: https://www.codingninjas.com/studio/problems/ninja-and-the-second-order-elements_6581960?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION

# Solution: 

```

/*
    Time complexity: O(N * Log(N))
    Space complexity: O(1)

    Where 'N' is the input array 'A'.
*/

vector<int> getSecondOrderElements(int n, vector<int> a) {
    // Sorting out the given input array.
    sort(a.begin(), a.end());
    return {a[n - 2], a[1]};
}



```

--------------------------------------------------------------------------------------------------------

# Problem 2

# Link: https://www.codingninjas.com/studio/problems/ninja-and-the-sorted-check_6581957?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION

# Code:

```
/*
    Time complexity: O(N)
    Space complexity: O(1)

    Where 'N' is the input array 'A'.
*/

int isSorted(int n, vector<int> a) {
    // Iterating over the array 'A'.
    for (int i = 0; i < n - 1; i++) {
        if (a[i + 1] < a[i]) {
            return 0;
        }
    }

    return 1;
}


```

----------------------------------------------------------------------------------------------------------------------------

# Problem 3 : LEETCODE

# Link: https://leetcode.com/problems/check-if-array-is-sorted-and-rotated/description/           
# Link: https://www.codingninjas.com/studio/problems/ninja-and-the-sorted-check_6581957?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION

# Code: 

```

#LEETCODE
class Solution {
public:
    bool check(vector<int>& nums) {
        int n=nums.size();
        int cnt=0;
        for(int i=1;i<n;i++){
            if(nums[i-1]>nums[i]){
                cnt++;
            }
        }
        if(nums[n-1]>nums[0]){
            cnt++;
        }
        return cnt<=1;
    }
};

```

```

# Coding Ninja
/*
    Time complexity: O(N)
    Space complexity: O(1)

    Where 'N' is the input array 'A'.
*/

int isSorted(int n, vector<int> a) {
    // Iterating over the array 'A'.
    for (int i = 0; i < n - 1; i++) {
        if (a[i + 1] < a[i]) {
            return 0;
        }
    }

    return 1;
}

```


----------------------------------------------------------------------------------------------------------


