![image](https://github.com/SpandanM110/DSA-kickstart/assets/95229740/fe5bbbec-fc07-4009-ba1f-b572dd95c4c2)

#Learning of the day use 3 signs of this ` at start and finish to look like a code snippet 

Code 1:
# For Vector arr use arr.size() instead in cases initially use arr.length

Cpp Code:
```
void selectionSort(vector<int>&arr) {
    // Write your code here.
    for(int i=0;i<arr.size() -1;i++){
        int min = i;
        for(int j = i+1;j<arr.size();j++){
            if(arr[j]<arr[min]){
                min = j;
            }
        }
        int temp = arr[min];
        arr[min] = arr[i];
        arr[i]= temp;
    }
}
```
------------------------------------------------------------------

![image](https://github.com/SpandanM110/DSA-kickstart/assets/95229740/f86c2907-1d98-4a41-ab4c-72c643899412)

Code 2:
Cpp Code:
``` 
/*
    Time Complexity : O(n ^ 2)
    Space Complexity : O(1)
    where n is size of the input array
*/
void bubbleSort(vector<int>& arr, int n) {
	for (int i = 0; i < n - 1; i++)
	{
		for (int j = 0; j < n - i - 1; j++)
		{
			// If jth element is greater than 'j + 1' th element
			// swap them
			if (arr[j] > arr[j + 1])
			{
				int tmp = arr[j];
				arr[j] = arr[j + 1];
				arr[j + 1] = tmp;
			}
		}
	}
}




```
-----------------------------------------------------------------------------------------------------------
![image](https://github.com/SpandanM110/DSA-kickstart/assets/95229740/be00b70f-5dbb-45c4-b84b-f6afd55a5489)

Code 3:

```
void insertionSort(int arr[], int n)
{
    //write your code here
    for(int i=0;i<n;i++){
        int j = i;
        while(j>0 && arr[j-1]>arr[j]){
            int temp = arr[j-1];
            arr[j-1] = arr[j];
            arr[j] = temp;
            j--;
        }
    }
}
```
---------------------------------------------------------------------------------------

# Question Link: https://www.codingninjas.com/studio/problems/merge-sort_5846?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION

![image](https://github.com/SpandanM110/DSA-kickstart/assets/95229740/9d54da08-44a2-4361-a0b7-d998d734ccc4)


Code 4:

```
/*  
    Time Complexity : O(n * log(n))
    Space Complexity : O(n)
    where n is size of input array
*/

void merge(vector<int>& arr, int l, int m, int r)
{
    // Stores the number of elements in the first half
    int num1 = m - l + 1;
    // Stores the number of elements in the second half
    int num2 =  r - m;

    // Creating two temporary arrays of size
    // 'num1' and 'num2' respectively.
    vector<int> L(num1), R(num2); 

    // Copy data to temporary arrays
    for(int i = 0; i < num1; ++i) {
        L[i] = arr[l + i];
    }
    for(int j = 0; j < num2; ++j) {
        R[j] = arr[m + 1 + j];
    }

    // Merge the temporary arrays back into 
    // arr[l ... r]
    
    int i = 0; // Initial index of the first subarray
    int j = 0; // Initial index of the second subarray
    int k = l; // Initial index of the merged subarray
    while (i < num1 && j < num2)
    {
        // If the current element in array 'L'
        // is less than current element in array 'R'
        // assign the current element of 'arr' to current
        // element of 'L' and increase index 'k' and 'i'.
        if (L[i] < R[j])
        {
            arr[k] = L[i];
            i++;
        }
        // assign the current element of 'arr' to current
        // element of 'R' and increase index 'k' and 'j'.
        else
        {
            arr[k] = R[j];
            j++;
        }
        k++;
    }

    // Copy the remaining elements of array 'L' to array
    // 'arr'
    while (i < num1)
    {
        arr[k] = L[i];
        i++;
        k++;
    }

    // Copy the remaining elements of array 'R' to array
    // 'arr'
    while (j < num2)
    {
        arr[k] = R[j];
        j++;
        k++;
    }
}
void mergeSort(vector<int>& arr, int l, int r) {
    
    // This means that there is atleast one element
    if(l < r) {
        // Finding the mid point
        int m = (l + r) / 2;
        
        // Sorting the first and second halves
        mergeSort(arr, l, m);
        mergeSort(arr, m + 1, r);
        
        // Merging the two sorted arrays
        merge(arr, l, m, r);
    }
}

```
-------------------------------------------------------------------------------------------------------------------
