#include <bits/stdc++.h>

using namespace std;

bool isSafe(int row,int col,vector<vector<int>>&sudoku,int num){
    
    for(int i=0;i<9;i++){
        if(sudoku[row][i]==num) return false;
        
        if(sudoku[i][col]==num)  return false;
        
        if(sudoku[ 3*(row/3) + i/3] [ 3*(col/3) + i%3 ] == num )  return false;
    }
    
    return true;
    
}

bool solve(vector<vector<int>>&sudoku){
    int n=sudoku[0].size();
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
            if(sudoku[i][j]==0){
                for(int k=1;k<=9;k++){
                    if(isSafe(i,j,sudoku,k)){
                        sudoku[i][j]=k;
                    
                    
                        bool further=solve(sudoku);
                        if(further) return true;
                        else sudoku[i][j]=0;
                    }
                }
                return false;
            }
        }
    }
    
    return true;
   
}

int main(){

    Start: 

    cout<<"Type 'Start' to start "<<endl;
    
    string s;
    cin>>s;
    
    if(s=="Start" || s=="start" || s=="START") {
        cout<<"ENTER A 9X9 MATRIX WITH BLANKS REPLACED BY 0"<<endl;
        vector<vector<int>>sudoku;
        for(int i=0;i<9;i++){
            vector<int>temp;
            for(int j=0;j<9;j++){
                int num;
                cin>>num;
                temp.push_back(num);
            }
            sudoku.push_back(temp);
        }
        
        
        Option:
        
        cout<<"------------------------Type HINT to see the hint--------------------- "<<endl;
        cout<<"-----------------------------OR-----------------------------------------  "<<endl;
        cout<<"--------------------Type SOLUTION to see the solution-------------------"<<endl;
        
        string n;
        cin>>n;
        if(n=="solution" || n=="Solution" || n=="SOLUTION"){
            
            
            solve(sudoku);
        
            for(int i=0;i<9;i++){
                vector<int>temp;
                for(int j=0;j<9;j++){
                  cout<<sudoku[i][j]<<" ";
                }
                cout<<endl;
            }
            
        }
        
        else if(n=="hint" || n=="HINT" || n=="Hint"){
            cout<<"A Sudoku Solution must satisfy three conditions : " <<endl;
            cout<<"1. Each of the digits 1-9 must occur exactly once in each row."<<endl;
            cout<<"2. Each of the digits 1-9 must occur exactly once in each column."<<endl;
            cout<<"3. Each of the digits 1-9 must occur exactly once in each of the 9, 3X3 grids of the grid ."<<endl;
            
            goto Option;
        }
        
        
        else{
            goto Option;
        }
        
        
        
    }
    else{
        goto Start;
    }
    

    return 0;
}
