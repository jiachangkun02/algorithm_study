![image-20241127075223387](C:\Users\jiachangkun\AppData\Roaming\Typora\typora-user-images\image-20241127075223387.png)

这题看似简单，代码写出来一测 便只有部分正确。便去问问ai哪里处问题了，结果ai连题目都解读错了，先在这留着，日后再回来看看是否有思路，部分正确代码如下

#include<iostream>
#include<vector>
using namespace std;

int main()
{
	int n;
	
	cin>>n;
	vector<int> v(n),a;
	int count=0;
	
	for(int i=0;i<n;i++){
		cin>>v[i];
	}
	auto it=v.begin();
	while(it!= v.end()){

        if(it==v.begin() && it==v.end()-1)
        {
            count++;
            a.push_back(*it);
            
        }
    	if(*it<*(it+1) && it==v.begin() && it!=v.end()-1){
    		count++;
    		a.push_back(*it);
    	}
    	if(*it<*(it+1) && *it>*(it-1) && it !=v.begin()){
    		count++;
    		a.push_back(*it);
    	}
    	if(*it>*(it-1) && it==v.end()-1){
    		count++;
    		a.push_back(*it);
    	}
        
    		it++;
	}
	auto ita=a.begin();
	cout<<count<<endl;
	while(ita!= a.end()){
		if(ita!=a.end()-1){
			cout<<*ita<<" ";
		}
		else
		{
			cout<<*ita;
		}
		ita++;
	}
	cout<<endl;
	
	return 0;
}