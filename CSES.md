# CSES

## Day 1 

### Weird ALgorithm 

just basic simulation 

'''cpp
   #include<bits/stdc++.h> 
   using namespace std; 
   #define deb(x) cout <<"\n"<< (#x) << " = " << (x) << "\n"
   const long long  INF = 1e18;
   const long long mod=1e9+7 ;
   #define ll long long int
   void inputoutput()
   {
      ios_base::sync_with_stdio(0);
      cin.tie(0); 
      #ifndef ONLINE_JUDGE
      freopen("input.txt", "r", stdin);
      freopen("output.txt", "w", stdout);
      #endif
          
   }



   void solve()
   {
      ll n;
      cin>>n;
      cout<<n<<" ";
      while(n>1)
      {
        if(n%2==1)
        {
          n=n*3+1;
        }
        else
          n=n/2 ;
        cout<<n<<" ";
      }
   }

   int main()
   { 
     inputoutput() ;

     int t=1;
     // cin>>t;
     while(t--)
      solve();
      
      return 0;
   }

   /*

   */
   
   

