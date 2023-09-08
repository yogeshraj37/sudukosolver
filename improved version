#include <bits/stdc++.h>
using namespace std;

vector<string> arr(9);

int board[9][9];

bool check(int row,int col,int x){
    for(int i=0;i<9;i++){
        if(board[row][i]==x){
            return false;
        }
        if(board[i][col]==x){
            return false;
        }
    }
    int br = (row/3)*3;
    int bc = (col/3)*3;
    for(int i=0;i<3;i++){
       for(int j=0;j<3;j++){
           if(board[br+i][bc+j]==x)return false;
       } 
    }
    return true;
}

void rec(int i,int j){
    // base case
    if(i==9){
        // print
        for(int i=0;i<9;i++){
            for(int j=0;j<9;j++){
                cout<<board[i][j]<<" ";
            }
            cout<<endl;
        }
        return;
    }
    // recursive case
    // choice
    if(arr[i][j]=='.'){
        for(int ch=1;ch<=9;ch++){
            // check
            if(check(i,j,ch)){
                // move
                board[i][j] = ch;   
                if(j<8)rec(i,j+1);
                else rec(i+1,0);
                board[i][j] = 0;
            }
        }
    }else{
        int ch = (arr[i][j]-'0');
        // check
        if(check(i,j,ch)){
            // move
            board[i][j] = ch;   
            if(j<8)rec(i,j+1);
            else rec(i+1,0);
            board[i][j] = 0;
        }
    }
}
// 

int main()
{
    // for(int i=0;i<9;i++){
    //     cin>>arr[i];
    // }
    
    arr = {
        "9.68.....",
        ".5..496.2",
        "4732.6..9",
        "...1329.7",
        "7.459..1.",
        "..9......",
        "..2.15.68",
        "56...73.1",
        "1..6..4..",
    };
    rec(0,0);
}
