#include <iostream>
#include <string>
using namespace std;

// Generic Binary Search Function
template <typename T>
int binarySearch(const T array[], int size, T key) {
    int low = 0, high = size - 1;
    
    while (low <= high) {
        int mid = low + (high - low) / 2;
        
        if (array[mid] == key)
            return mid; // Found, return index
        else if (array[mid] < key)
            low = mid + 1; // Search right half
        else
            high = mid - 1; // Search left half
    }
    
    return -1; // Not found
}

int main() {
    // Testing with int array
    int intArray[] = {1, 3, 5, 7, 9};
    int intKey = 7;
    cout << "Index of " << intKey << " in int array: " 
         << binarySearch(intArray, 5, intKey) << endl;

    // Testing with double array
    double doubleArray[] = {1.1, 3.3, 5.5, 7.7, 9.9};
    double doubleKey = 3.3;
    cout << "Index of " << doubleKey << " in double array: " 
         << binarySearch(doubleArray, 5, doubleKey) << endl;

    // Testing with string array (must be sorted alphabetically)
    string strArray[] = {"apple", "banana", "cherry", "date", "elderberry"};
    string strKey = "cherry";
    cout << "Index of \"" << strKey << "\" in string array: " 
         << binarySearch(strArray, 5, strKey) << endl;

    return 0;
}
