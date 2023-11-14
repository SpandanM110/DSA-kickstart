## Question 1
## Link: https://www.codingninjas.com/studio/problems/remove-duplicates-from-sorted-array_1102307?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION

## Code: 

```
int removeDuplicates(vector<int> &arr, int n) {
    if (n == 0 || n == 1) {
        return n;
    }
	// For the number of elements

	// Now for duplicates
    int i = 0;
    for (int j = 1; j < n; j++) {
        if (arr[i] != arr[j]) {
            i++;
            arr[i] = arr[j];
        }
    }
    return i + 1; // Returns i+1 unique elements
	//  where i is count of  unique elements
}

```
------------------------------------------------------------------------------------------------------------

## Question 2

## Link: https://www.codingninjas.com/studio/problems/left-rotate-an-array-by-one_5026278?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION

## Code

```
#include <bits/stdc++.h> 
vector<int> rotateArray(vector<int>& arr, int n) {
    if(n==1 || n==0){
        return arr;
    }
    int temp = arr[0];
    for(int i=0;i<n-1;i++){
        arr[i] = arr[i+1];
    }
    arr[n-1] = temp;
    return arr;
 
}


```
## Leet code: https://leetcode.com/problems/rotate-array/submissions/1098541299/

## Code:

```
class Solution {
public:
    void rotate(vector<int>& nums, int k) {
        int n = nums.size();
        k %= n; // To handle cases where k is greater than n

        // Reverse the entire array
        reverse(nums.begin(), nums.end());
        
        // Reverse the first k elements
        reverse(nums.begin(), nums.begin() + k);
        
        // Reverse the remaining elements
        reverse(nums.begin() + k, nums.end());
    }
};

```

-------------------------------------------------------------------------------------------------------------

## Question 3

## Link: https://www.codingninjas.com/studio/problems/rotate-array_1230543?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION

## Code

```
/*
    Time Complexity: O(n*k)
    Space Complexity: O(1)
    where n is the size of the input array.
*/

vector<int> rotateArray(vector<int> arr, int k) {
    int n = arr.size();
    for (int i = 0; i < k; i++) {
        int temp = arr[0];
        for (int j = 0; j < n - 1; j++) {
            arr[j] = arr[j + 1];
        }
        arr[n - 1] = temp;
    }

    return arr;
}


```

-----------------------------------------------------------------------------------------------------------------

## Question 4

## Link: https://www.codingninjas.com/studio/problems/ninja-and-the-zero-s_6581958?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION

## Code

```
vector<int> moveZeros(int n, vector<int> a) {
    // Write your code here.
    vector<int> temp;
    
    for (int i = 0; i < n; i++) {
        if (a[i] != 0) {
            temp.push_back(a[i]);
        }
    }

    // Fill remaining positions in 'a' with zeros
    for (int i = temp.size(); i < n; i++) {
        temp.push_back(0);
    }

    return temp;
}


```

-----------------------------------------------------------------------------------------------------------------

## Question 5

## Link: https://www.codingninjas.com/studio/problems/linear-search_6922070?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION

## Code

```
int linearSearch(int n, int num, vector<int> &arr)
{
    // Write your code here.
    if(n==0 || n==1){
        return -1;
    }
    for(int i=0;i<n;i++){
        if(arr[i]==num){
            return i;
        }

    }
    return -1;
}

```

---------------------------------------------------------------------------------------------------------------------

## Question 6

## Link: https://www.codingninjas.com/studio/problems/sorted-array_6613259?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION

## Code

```
/*
    Time Complexity: O((N + M) * log(N + M))
    Space Complexity: O(N + M)

    N and M are the sizes of array 'a' and 'b' respectively.
*/
#include <set>
vector < int > sortedArray(vector < int > a, vector < int > b) {

    int n = a.size(), m = b.size();
    // Using a min-heap to 
    // store all distinct elements
    set < int > st;

    // Iterating over 'a'
    for (int i = 0; i < n; ++i) {
        st.insert(a[i]);
    }

    // Iterating over 'b'
    for (int i = 0; i < m; ++i) {
        st.insert(b[i]);
    }

    vector < int > unionArray;

    // Copying all elements 
    // from the set to the vector
    for (const int & value: st) {
        unionArray.push_back(value);
    }

    return unionArray;
}
```

---------------------------------------------------------------------------------------------------------------------


## Question 7

## Link: https://leetcode.com/problems/missing-number/

## Code

```
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n = nums.size();
        int missing = n; // Initialize missing as the last expected number
        
        for (int i = 0; i < n; i++) {
            missing ^= i ^ nums[i]; // XOR operation to find the missing number
        }
        
        return missing; // Return the missing number
    }
};


```

---------------------------------------------------------------------------------------------------------------------


## Question 8

## Link: https://www.codingninjas.com/studio/problems/traffic_6682625?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SOLUTION

## Code

```
/*
    Time Complexity : O( N )
    Space complexity: O( 1 )

    Where N is the size of the vehicle array.
*/

int traffic(int n, int m, vector<int> vehicle) {
	// Create ans, count and right, and assign with 0.
	int ans = 0, count = 0, right = 0 ;
	// For loop to move the left pointer.
	for(int left = 0; left < n; left++)
    {
        // while right is less than n and count is <= m.
        while(right < n && count <= m)
        {
            // If vehicle at right is 0.
            if(vehicle[right] == 0)
            {
                count++ ;
                // Break if count exceeds m.
                if(count > m)
                {
                    count-- ;
                    break ;
                }
            }
            right++ ;
        }
        // Update answer.
        ans = max(ans, right-left) ;
        // If vehicle at left is 0.
        if(vehicle[left] == 0)
        {
            count-- ;
        }
    }
    // Return answer.
    return ans ;
}


```

---------------------------------------------------------------------------------------------------------------------



## Question 9

## Link: https://www.codingninjas.com/studio/problems/find-the-single-element_6680465?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION

## Code

```
/*
Time Complexity: O(N ^ 2)

Space Complexity: O(1)

Where 'N' is the number of elements in the array 'Arr'.
*/

int getSingleElement(vector<int> &arr){
	int n = arr.size();
	int ans;
	
	// Traversing through the array.
	for(int i = 0; i < n; ++i){
		bool pass = 0;
		
		// Checking if there is another number in the array equal to 'Arr[i]'.
		for(int j = 0; j < n && !pass; ++j){
			if(i == j)
				continue;
			if(arr[i] == arr[j])
				pass = 1;
		}
		
		// If there is no element equal to 'Arr[i]', then 'Arr[i]' is the answer.
		if(!pass)
			ans = arr[i];
	}
	return ans;
}

```

---------------------------------------------------------------------------------------------------------------------
