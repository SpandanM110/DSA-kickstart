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




