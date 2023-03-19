# project
Programming with C

Here are four different functions/procedures to sort an array in descending order in C:

Function 1: Bubble Sort

void bubbleSort(int arr[], int n) {
  for (int i = 0; i < n-1; i++) {
    for (int j = 0; j < n-i-1; j++) {
      if (arr[j] < arr[j+1]) {
        int temp = arr[j];
        arr[j] = arr[j+1];
        arr[j+1] = temp;
      }
    }
  }
}

Function 2: Selection Sort

void selectionSort(int arr[], int n) {
  int i, j, max_idx;
  for (i = 0; i < n-1; i++) {
    max_idx = i;
    for (j = i+1; j < n; j++) {
      if (arr[j] > arr[max_idx]) {
        max_idx = j;
      }
    }
    int temp = arr[i];
    arr[i] = arr[max_idx];
    arr[max_idx] = temp;
  }
}

Function 3: Insertion Sort

void insertionSort(int arr[], int n) {
  int i, key, j;
  for (i = 1; i < n; i++) {
    key = arr[i];
    j = i - 1;
    while (j >= 0 && arr[j] < key) {
      arr[j+1] = arr[j];
      j = j - 1;
    }
    arr[j+1] = key;
  }
}

Function 4: Quick Sort

void swap(int* a, int* b){
    int t = *a;
    *a = *b;
    *b = t;
}

int partition(int arr[], int low, int high){
    int pivot = arr[high];
    int i = (low - 1);
    for (int j = low; j <= high- 1; j++){
        if (arr[j] >= pivot){
            i++;
            swap(&arr[i], &arr[j]);
        }
    }
    swap(&arr[i + 1], &arr[high]);
    return (i + 1);
}

void quickSort(int arr[], int low, int high){
    if (low < high){
        int pi = partition(arr, low, high);
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}
