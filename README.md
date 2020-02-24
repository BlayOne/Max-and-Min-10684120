
#include <iostream>

using namespace std;

void swap(int *mn, int *qr) 
{ 
    int temp = *mn; 
    *mn = *qr; 
    *qr = temp; 
} 

void bubbleSort(int arr[], int size) 
{ 
   int i, j; 
   bool swapped; 
   for (i = 0; i < size-1; i++) 
   { 
     swapped = false; 
     for (j = 0; j < size-i-1; j++) 
     { 
        if (arr[j] > arr[j+1]) 
        { 
           swap(&arr[j], &arr[j+1]); 
           swapped = true; 
        } 
     } 
  
     // IF no two elements were swapped by inner loop, then break 
     if (swapped == false) 
        break; 
   } 
} 

int main(void){
    int size;
    cout << "Enter the size of the array here: ";
    cin >> size;
    int arr[size];
    
    cout << "Enter the elements of the array: " <<endl;
    for(int i = 0; i<size; i++){
        cin >> arr[i];
    }

    bubbleSort(arr, size);

    int max = arr[size-1];
    int min = arr[0];

    cout << "The biggest number is " << max <<endl;
    cout << "The smallest number is " << min <<endl;

    return 0;
    }
