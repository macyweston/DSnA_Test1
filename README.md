//# DSnA_Test1
#include <cstdlib> 
#include <ctime> 
#include <iostream>

using namespace std;

void main() 
{ 

 const int n;
 cout<< "how big do you want the array?" << endl;
 cin >> n;
 int *a = new int[n];
 
 srand((unsigned)time(NULL)); 
     
  for(int i=0; i<n; i++){ 
      *a[i] = (rand()%10)+1; 
  } 

  for (int i = 1; i < 25; i++) {
      cout << *a[i];
  }

  for (int i = 1; i < n; i++) {// insert a[i] into a[0:i-1]
     int t = *a[i];
     int j;
     for (j = i - 1; j >= 0 && t < *a[j]; j--)
         *a[j + 1] = *a[j];
     *a[j + 1] = t;
  }
  
  for (int i = 1; i < 25; i++) {
      cout << *a[i];
  }
  
  delete[] *a;
}
