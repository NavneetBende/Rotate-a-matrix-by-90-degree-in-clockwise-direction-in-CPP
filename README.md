Rotate a matrix by 90 degree in clockwise direction in C++
Here, in this page we will discuss the program to rotate a matrix by 90 degree in clockwise direction in C++ Programming Language. We are given with matrix and we need to print the rotated matrix. We will discuss the approaches that solve this problem in constant space.

Example :

Input :  [{1, 2, 3}, {4, 5, 6}, {7, 8, 9}]
Output :  [{7, 4, 1} {8, 5, 2} {9, 6, 3}]
.

Rotate a matrix by 90 degree in clockwise direction in C++
Method 1 :
First transpose the matrix.
For this run a loop from i=0 to n and another loop from j=i+1 to j<n and swap(mat[i][j], mat[j][i]).
After doing this, now iterate over rows and reverse each rows.
After this print the entire matrix (that gets rotated).
Time and Space Complexity :
Time-Complexity : O(n*n)
Space-Complexity : O(1)
Rotate the matrix in C++
Code to rotate a matrix by 90 degree in clockwise direction in C++
Run
#include<bits/stdc++.h>
using namespace std;
int main(){

   int n=4;
   int mat[n][n]= { { 1, 2, 3, 4 },{ 5, 6, 7, 8 },{ 9, 10, 11, 12 },{ 13, 14, 15, 16 } };

   //Tranposing the matrix
   for(int i=0; i<n; i++){
     for(int j=i+1; j<n; j++)
         swap(mat[i][j], mat[j][i]);
    }

   //Reversing each row of the matrix
   for(int i=0; i<n; i++){
     for(int j=0; j<n/2; j++){
        swap(mat[i][j], mat[i][n-j-1]);
     }
   }

   //Print the matrix
   cout<<"Rotated Matrix :\n";
   for(int i=0; i<n; i++){
     for(int j=0; j<n; j++){
       cout<<mat[i][j]<<" ";
     }
     cout<<endl;
   }
}
Output
Rotated Matrix is :
13 9 5 1
14 10 6 2
15 11 7 3
16 12 8 4
Method 2 :
First rotate the matrix about its main diagonal.
For this run a loop from i=0 to n and another loop from j=0 to 1, and swap (mat[i][j], mat[j][i])
Now, rotate the matrix about middle column.
For this run a loop from i=0 to n, and another loop from j=0 to n/2 and swap (mat[i][j],, mat[i][n-j-1]).
After this print the entire matrix (that gets rotated).
Time and Space Complexity :
Time-Complexity : O(n*n)
Space-Complexity : O(1)
Code to rotate a matrix by 90 degree in clockwise direction in C++
Run
#include<bits/stdc++.h>
using namespace std;

int main(){

   int n=4;
   int mat[n][n]= { { 1, 2, 3, 4 },{ 5, 6, 7, 8 },{ 9, 10, 11, 12 },{ 13, 14, 15, 16 } };

   //Rotate the matrix about the main diagonal
   for(int i=0; i<n; i++){
     for(int j=0; j<i; j++)
         swap(mat[i][j], mat[j][i]);
    }

   //Rotate the matrix about middle column
   for(int i=0; i<n; i++){
     for(int j=0; j<n/2; j++){
        swap(mat[i][j], mat[i][n-j-1]);
     }
   }

   //Print the matrix
   cout<<"Rotated Matrix :\n";
   for(int i=0; i<n; i++){
     for(int j=0; j<n; j++){
       cout<<mat[i][j]<<" ";
     }
     cout<<endl;
   }
}
Output
Rotated Matrix is :
13 9 5 1
14 10 6 2
15 11 7 3
16 12 8 4
Method 3 :
First rotate the matrix about its secondary diagonal.
For this run a loop from i=0 to n and another loop from j=0 to n-1, and swap (mat[i][j], mat[n-1-i][n-1-j])
Now, rotate the matrix about middle row.
For this run a loop from i=0 to n/2, and another loop from j=0 to n and swap (mat[i][j], mat[n-1-i][j]).
After this print the entire matrix (that gets rotated).
Time and Space Complexity :
Time-Complexity : O(n*n)
Space-Complexity : O(1)
Code to rotate a matrix by 90 degree in clockwise direction in C++
Run
#include<bits/stdc++.h>
using namespace std;

int main(){

   int n=4;
   int mat[n][n]= { { 1, 2, 3, 4 },{ 5, 6, 7, 8 },{ 9, 10, 11, 12 },{ 13, 14, 15, 16 } };

   //Rotate the matrix about the secondary diagonal
   for(int i=0; i<n; i++){
     for(int j=0; j<n-i; j++)
         swap(mat[i][j], mat[n-1-i][n-1-j]);
    }

   //Rotate the matrix about middle row
   for(int i=0; i<n/2; i++){
     for(int j=0; j<n; j++){
        swap(mat[i][j], mat[n-1-i][j]);
     }
   }

   //Print the matrix
   cout<<"Rotated Matrix :\n";
   for(int i=0; i<n; i++){
     for(int j=0; j<n; j++){
       cout<<mat[i][j]<<" ";
     }
     cout<<endl;
   }
}
Output
Rotated Matrix is :
13 9 5 1
14 10 6 2
15 11 7 3
16 12 8 4
While loop in C
