#include<bits/stdc++.h>
using namespace std;
int main(){
	int n,m; cin >> n >>m;
	int a[n], b[m];
	for(int i = 0; i< n; i++){
		cin >> a[i];
	}
	for(int i = 0; i< m; i++){
		cin >> b[i];
	}
	int i = 0, j = 0; 
	long long dem = 0;
	while(i < n && j < m){
		if( a[i] == b[j]) {
			int x = a[i];
		     int demA = 0, demB = 0;
		     while(i < n && x == a[i])
		     {
		     	demA++;
		     	++i;
			 }
			 while(j < m && x == b[j])
		     {
		     	demB++;
		     	++j;
			 }
			 dem += (long long)(demA * demB);
		   }
		else if(a[i] > b[j]) j++;
		else i++;
	}
	cout << dem << endl;
}




//cach2
#include<bits/stdc++.h>
using namespace std;
int main(){
	int n,m; cin >> n >>m;
	int a[n], b[m];
	map<int,int> mpA, mpB;
	for(int i = 0; i< n; i++){
		cin >> a[i];
		mpA[a[i]]++;
	}
	for(int i = 0; i< m; i++){
		cin >> b[i];
		mpB[b[i]]++;
	}
	int dem = 0;
	for(auto it : mpA){
		auto it1 = mpB.find(it.first);{
			if(it1 != mpB.end()){
				dem += (*it1).second * it.second;
			}
		}
	}
	cout << dem << endl;
}
	
