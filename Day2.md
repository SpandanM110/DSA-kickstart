---------------------------------------------------------------------------------------------------------------------
# Recursive Bubble Sort

Doc Link: https://takeuforward.org/arrays/recursive-bubble-sort-algorithm/

# Code:

```
#include <bits/stdc++.h>
using namespace std;

void bubble_sort(int arr[], int n) {
    // Base Case: range == 1.
    if (n == 1) return;

    for (int j = 0; j <= n - 2; j++) {
        if (arr[j] > arr[j + 1]) {
            int temp = arr[j + 1];
            arr[j + 1] = arr[j];
            arr[j] = temp;
        }
    }

    //Range reduced after recursion:
    bubble_sort(arr, n - 1);
}

int main()
{
    int arr[] = {13, 46, 24, 52, 20, 9};
    int n = sizeof(arr) / sizeof(arr[0]);
    cout << "Before Using Bubble Sort: " << endl;
    for (int i = 0; i < n; i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;

    bubble_sort(arr, n);
    cout << "After Using bubble sort: " << "\n";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    cout << "\n";
    return 0;

}
```
--------------------------------------------------------------------------------------------------------------------------

# Recursive Insertion Sort

Doc Link: https://takeuforward.org/arrays/recursive-insertion-sort-algorithm/

# Code:

```
#include <bits/stdc++.h>
using namespace std;

void insertion_sort(int arr[], int i, int n) {

    // Base Case: i == n.
    if (i == n) return;

    int j = i;
    while (j > 0 && arr[j - 1] > arr[j]) {
        int temp = arr[j - 1];
        arr[j - 1] = arr[j];
        arr[j] = temp;
        j--;
    }

    insertion_sort(arr, i + 1, n);
}

int main()
{
    int arr[] = {13, 46, 24, 52, 20, 9};
    int n = sizeof(arr) / sizeof(arr[0]);
    cout << "Before Using insertion Sort: " << endl;
    for (int i = 0; i < n; i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;

    insertion_sort(arr, 0, n);
    cout << "After Using insertion sort: " << "\n";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    cout << "\n";
    return 0;
}
```
----------------------------------------------------------------------------------------------------

# Quick Sort 
![image](https://github.com/SpandanM110/DSA-kickstart/assets/95229740/1b9713c4-3c94-4ee0-8924-43a1fce49bb8)

Link: https://www.codingninjas.com/studio/problems/quick-sort_5844?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION

Doc: https://takeuforward.org/data-structure/quick-sort-algorithm/



Code:
```


int partitionArray(int input[], int start, int end) {
    int pivot = input[start];
    int i = start;
    int j = end;

    while (i < j) {
        while (input[i] <= pivot && i <= end - 1) {
            i++;
        }
        while (input[j] > pivot && j >= start + 1) {
            j--;
        }
        if (i < j) {
            std::swap(input[i], input[j]);
        }
    }
    std::swap(input[start], input[j]);
    return j;
}

void quickSort(int input[], int start, int end) {
    if (start < end) {
        int pindex = partitionArray(input, start, end);
        quickSort(input, start, pindex - 1);
        quickSort(input, pindex + 1, end);
    }
}

```
----------------------------------------------------------------------------------------------------------

# Array Questions

![image](https://github.com/SpandanM110/DSA-kickstart/assets/95229740/d8943403-dcba-47e6-9279-0cf702fb33db)

Link: https://www.codingninjas.com/studio/problems/largest-element-in-the-array-largest-element-in-the-array_5026279?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION


Doc: https://takeuforward.org/data-structure/find-the-largest-element-in-an-array/


Code:

'''

    #include <bits/stdc++.h> 
    int largestElement(vector<int> &arr, int n) {
    int max=arr[0];
    for(int i =0; i<n;i++){
        
        if(max<arr[i]){
            max=arr[i];
        }
    }
    return max;   
    }

'''

------------------------------------------------------------------------------------------------------------------------















