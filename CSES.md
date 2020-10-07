# CSES

## Day 1 

### 1)Weird ALgorithm 

just basic simulation 

```cpp
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
   ```
   ### 2)Missing Number 
   sum formula property 
   ```cpp
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
      ll n ;
      cin>>n ;
      ll sum=0 ;
      for(ll i=0 ; i<n-1 ; ++i)
      {
        ll x ;
        cin>>x;
        sum+=x;
      }

      cout<<(n*(n+1)/2-sum);
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
   ```
   ### 3) Repetetions 
   
   keeping track of all maximums , remember to check for maximum in the last suffix 
   
   ```cpp
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
      string s;
      cin>>s ;
      ll ans=0 ;
      ll rep=1 ;

      for(ll i=1 ; i<s.size() ; ++i)
      {
        if(s[i]==s[i-1])
        {
          ++rep;
          continue;
        }
        else
        {
          ans=max(ans,rep);
          rep=1;
        }
      }
      ans=max(ans,rep);
      cout<<ans<<"\n";
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
   ```
   
   ### 4)Increasing array 
   
   keep track of the current maximum , if new x is lower add the diff. to answerr
   
   ```cpp
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
      ll ans=0;
      
      ll x ;
      cin>>x ;
      ll cmax=x ;

      for(int i=1 ; i<n ; ++i)
      {
        cin>>x;
        if(x>=cmax)
        {
          cmax=max(cmax,x);
          continue;
        }
        else
        {
          ans+=cmax-x;
        }
      }
      cout<<ans<<"\n";


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
   ```
   
   ### 5)Permutations
   
   special case 1,2,3,4  , for rest print alternating sequences from 1 and 2
   
   ```cpp
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
      int n;
      cin>>n;

      if(n==1)
      {
        cout<<"1";
      }
      else if(n==2 || n==3)
      {
        cout<<"NO SOLUTION";
      }
      else if(n==4)
      {
        cout<<"2 4 1 3";
      }
      else 
      {
        for(int i=1 ; i<=n ; i+=2)
          cout<<i<<" ";
        for(int i=2 ; i<=n ; i+=2)
          cout<<i<<" ";

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
   ```
   ### 6)Number Spiral
   
   requires observation , we have two cases y>x or x>y   , then we find the max element that possibly could be in that row (squared observation) 
   then we decrease or increase x by odd/even observation (this problem sucks)
   ```cpp
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
      ll x,y;
      cin>>x>>y ;
      // 2 3

      if(x<y)
      { 
        if(y%2==1)
        {
          cout<<y*y-x+1 ;
        }
        else
        {
          cout<<(y-1)*(y-1)+1+x-1 ;
        }
        cout<<"\n";
      }
      else
      {
        if(x%2==1)
        {
          cout<<(x-1)*(x-1)+1+y-1 ;
        }
        else
        {
          cout<<x*x-y+1 ;
        }
        cout<<"\n";
      }



   }

   int main()
   { 
     inputoutput() ;

     int t=1;
     cin>>t;
     while(t--)
      solve();
      
      return 0;
   }

   /*

   */
   ```
### 7) Two Knights ( not the actual solution )

   used Pattern solver to find formula from wolfram alpha to solve this :-))
   
   ```cpp
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
      unsigned ll n ;
      cin>>n;
      for(unsigned ll i=1 ; i<=n ; ++i)
      {
          cout<<(i*i*i*i-9*i*i+24*i-16)/2<<"\n";
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

      k==1 
            0 , two knights cannot be placed in one cell
      k==2 
                  
   */
   ```
   
   
   
   
   
   
   
   
   
   
   
   
   

