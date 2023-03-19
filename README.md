# first-project-
Programming with C

1.C Program to Sort Array in Descending Order

#include <stdio.h>
int main()
{
	int Array[50], i, j, temp, Size;
	
	printf("\nPlease Enter the Number of elements in an array  :  ");
	scanf("%d", &Size);
	
	printf("\nPlease Enter %d elements of an Array \n", Size);
	for (i = 0; i < Size; i++)
	{
		scanf("%d", &Array[i]);
    }     
	for (i = 0; i < Size; i++)
	{
		for (j = i + 1; j < Size; j++)
		{
			if(Array[i] < Array[j])
			{
				temp = Array[i];
				Array[i] = Array[j];
				Array[j] = temp;
			}
			
		}
	}
	printf("\n **** Array of Elemenst in Descending Order are : ****\n");
	for (i = 0; i < Size; i++)
	{
		printf("%d\t", Array[i]);
	}
	
	return 0;
}

2.C Program to Sort Array in Descending Order using Functions
#include <stdio.h>
int *Sort_ArrayDesc(int arr[], int Size);
int main()
{
	int Array[50], i, j, Size;
	int *arr;
	
	printf("\nPlease Enter the Number of elements in an array  :  ");
	scanf("%d", &Size);
	
	printf("\nPlease Enter %d elements of an Array \n", Size);
	for (i = 0; i < Size; i++)
	{
		scanf("%d", &Array[i]);
    }  
	
	arr = Sort_ArrayDesc(Array, Size);   
	printf("\n **** Array of Elemenst in Descending Order are : ****\n");
	for (i = 0; i < Size; i++)
	{
		printf(" Element at Array[%d] = %d \n", i, arr[i]);
	}	
	return 0;
}
int *Sort_ArrayDesc(int arr[], int Size)
{
	int i, j, temp;
	
	for (i = 0; i < Size; i++)
	{
		for (j = i + 1; j < Size; j++)
		{
			if(arr[i] < arr[j])
			{
				temp = arr[i];
				arr[i] = arr[j];
				arr[j] = temp;
			}			
		}
	}
	return arr;	
}

3.
// C program to sort array elements in descending order
// using functions
  
#include <stdio.h>
// defining the function
int desc_order(int a[10], int n)
{
    int i, j, t = 0;
    
    // iterates the array elements
    for (i = 0; i < n; i++) {
        
        // iterates the array elements from index 1
        for (j = i + 1; j < n; j++) {
            
            // comparing the array elements, to set array
            // elements in descending order
            if (a[i] < a[j]) {
                t = a[i];
                a[i] = a[j];
                a[j] = t;
            }
        }
    }
    // printing the output
    for (i = 0; i < n; i++) {
        printf("%d ", a[i]);
    }
    return 0;
}
int main()
{
    int arr[5] = { 45, 22, 100, 66, 37 };
    int num = 5;
    
    // calling the function
    desc_order(arr, num);
}
