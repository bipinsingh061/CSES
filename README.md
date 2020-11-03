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
   ### 6)Number Spiral ( too much observation required )
   
   requires observation , we have two cases y>x or x>y   , then we 
   
   the max element that possibly could be in that row (squared observation) 
   then we decrease or increase x by odd/even observation 
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
   
   ### 8) Two Sets 
   
   if total sum till n is odd not possible to divide , otherwise yes and go greedy
   
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
      cin>>n;

      ll tsum=n*(n+1)/2 ;

      if(tsum%2==1)
      {
        cout<<"NO\n";
      }
      else
      {
        tsum/=2 ;
        // two sets of sum tsum , tsum 
        vector<ll> a,b ;
        while(n)
        {
          if(tsum-n>=0)
          {
            a.push_back(n);
            tsum-=n;
          }
          else
          {
            b.push_back(n);
          }
          --n;
        }
        cout<<"YES\n";
        cout<<a.size()<<"\n";
        for(auto i : a)
          cout<<i<<" ";
        cout<<"\n";
        cout<<b.size()<<"\n";
        for(auto i : b)
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
   
   ### 9) Bit Strings
   
   2^n using mod every time
   
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
      unsigned ll n;
      cin>>n;
      unsigned ll res=1 ;
      for(int i=1 ; i<=n ; ++i)
        res=res*2%mod;
      cout<<res ;
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
   ### 10) Trailing Zeroes 
   
   only prime factors 5's and 2's contribute to a zero , also the number of 5's is lesser than 2's  , for given n we find out the number of factors of 5,25,125 etc
   
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
      cin>>n;

      ll ans=0 ;
      ll k=5 ;
      while(n/k>0)
      {
        ans+=n/k ;
        k*=5;
      }
      cout<<ans;

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
      1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

      20/5 = 4

      5,10,15,20 
      n/5

                  
   */
   ```
   
   ### 11) Coin Piles
   
   since in each move we take 3 coins , the total coins should be a multiple of 3 , also minimum of both the piles should be atleast half the other pile , 
   because we take 1 from one pile and 2 from other 
   
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
      ll a,b;
      cin>>a>>b;

      if(a>b)
        swap(a,b);

      if((a+b)%3==0 && a>=b/2)
        cout<<"YES\n";
      else
        cout<<"NO\n";

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
      1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

      20/5 = 4

      5,10,15,20 
      n/5

                  
   */
   ```
   ### 12) Palindrome Reorder 
   
   if has even string size each count of character must be zero , keep another string store alternate counts print, reverse and print again ,  if size odd there must be only 1 character with odd count store this character and remove from a  , print a , mid , rev(a)
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
      string s ;
      cin>>s ;

      int n=s.size()  ;
      char mid ;
      map<char,int> mp ;
        string a;
        for(auto i : s)
        {
          mp[i]++ ;
          if(mp[i]%2==1)
            a.push_back(i);
        }
        int odds=0;
        for(auto i : mp)
        {
          if(i.second%2==1)
          {
            ++odds ;
            mid=i.first ;
          }
        }

      if(n%2==0)
      {
        if(odds!=0)
        {
          cout<<"NO SOLUTION";
          return ;
        }
        else
        {
          cout<<a;
          reverse(a.begin(),a.end());
          cout<<a;
          return ;
        }
      }
      else
      {
        if(odds!=1)
        {
          cout<<"NO SOLUTION";
          return ;
        }
        else
        {
          // removing one char mid 
          for(int i=0 ; i<a.size() ; ++i)
          {
            if(a[i]==mid)
            {
              a.erase(a.begin()+i);
              break;
            }
          }
          cout<<a;
          reverse(a.begin(),a.end());
          cout<<mid;
          cout<<a;
        }
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
   ### 13) Creating Strings 
   
   used next_permutaion built in function , remember to sort the string then generate permutations
   
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
      string s ;
      cin>>s ;
      sort(s.begin(),s.end());
      vector<string> k ;

      do
      {
        k.push_back(s);
      }while(next_permutation(s.begin(),s.end()));
      cout<<k.size()<<"\n";
      for(auto i : k)
        cout<<i<<"\n";

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
   
   ### 14) Apple Division
   
   used bit manipulation to find all subsets of apples and found minimum difference
   
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
      cin>>n;
      vector<ll> a(n);
      ll sum=0;
      for(ll i=0 ; i<n ; ++i)
      {
        cin>>a[i];
        sum+=a[i];
      }
      ll ans=INT_MAX ;
      for(ll i=0 ; i< 1<<n  ; ++i)
      {
        ll tsum=0;
        for(ll j=0 ; j<n ; ++j)
        {
          if(i & 1<<j)
            tsum+=a[j];
        }
        ans=min(ans,abs(sum-tsum-tsum));
      }
      cout<<ans ;
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
   
   #### 15 ,16 not done 
   
   ## Day 2
   
   ### 17) Distinct Numbers 
   
   easy problem  , store all elements in set , print set size 
   
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
      set<ll> st ;
      for(ll i=0 ;i<n ; ++i)
      {
        ll x;
        cin>>x;
        st.insert(x);
      }
      cout<<st.size();
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
   
   
   ### 18) Apartments 
   
   used multisets to store apartment sizes  , also sorting the desired apartment sizes is important  , then for each desired apartment size found out the lower bound of a[i]-k , if it was in the range need deleted it ,
   
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
    
   ll n,m,k;
   vector<ll> a(2e5+1000,INF);
   multiset<ll> ms ;
 
   void solve()
   {
      cin>>n>>m>>k;
 
      for(ll i=0 ; i<n ; ++i)
        cin>>a[i];
      sort(a.begin(), a.end());
 
      for(ll i=0 ; i<m ; ++i)
      {
        ll x;
        cin>>x ;
        ms.insert(x);
      }
      ll ans=0;
      for(ll i=0 ; i<n ; ++i)
      {
        auto closest = ms.lower_bound(a[i]-k);
        if(*closest<=a[i]+k && *closest>=a[i]-k && closest!=ms.end())
        {
          ++ans;
          ms.erase(closest);
        }
      }
      cout<<ans;
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
      4 3 5
      60 45 80 60
      30 60 75    
 
      for any ai allowed sizes are  : 
 
      ai-k ...........ai-1 , ai , ai+1 ,ai+2 , ai+3 ,.......... ai+k
      also k is huge upto 10^9
 
      maybe binary search ai on array b(b is sorted) 
      and see if it works 
 
      4 3 5
      60 45 80 60
      30 60 75
 
      10 10 10
      90 41 20 39 49 21 35 31 74 86
      4 7 14 24 24 60 82 82 85 95   
      14 24 24 7 82 85 82 4 60 95
 
      
      4 3 5
      60 45 80 60
      30 75
      
  
   */
   ```
   ## Day 3 
   
   ### 19) Ferris Wheel
   
   do not overthink with multisets  , two pointer technique works fine 
   
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
      ll n,k;
      cin>>n>>k ;

      vector<ll> a(n);

      for(ll i=0 ; i<n ; ++i)
        cin>>a[i];
      sort(a.begin(),a.end());

      ll i=0 , j=n-1 ;
      ll ans=0;
      while(i<=j)
      {
        if(a[i]+a[j]>k)
          --j;
        else 
        {
          ++i;
          --j;
        }
        ++ans;
      }
      cout<<ans ;

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
        4 10
        7 2 3 9

        2 3 7 9


        10 15
        9 8 8 9 10 8 5 8 7 10

        5 7 8 8 8 8 9 9 10 10


        

   */
   ```
   
   ### 20) Conncert Tickets
   
   approach 1) (dumb approach) 
   
   
   this problem is basically finding multiple queries to the question : find maximum element less that or equal to a number  , also once found the answer the value can no longer be used in other queries  ( item is deleted ) 
   
   used a multiset to store ticket prices , went through each max. price of customer (x) , found lower bound and upper bounds of x , if answer to query doesn't exist it can be checked by condition  :
   
   lowerbound==upperbound  and  upperbound==ms.begin()
   
   then find if any of lower bound or upper bound points to exact val of x , push x   , if not then ,
   
   decrease upper_bound by 1 (--ub)  , and then check ub if its possible
   
   approach 2)   
   
   input elements in multiset in decreasing order then lower_bound returns max val less than or equal to x
  
   ### approach 1 (not good)
   
   
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
      ll n,m ;
      cin>>n>>m;
 
      multiset<ll> ms ;
 
      for(ll i=0 ; i<n ; ++i)
      {
        ll x;
        cin>>x;
        ms.insert(x);
      }
      vector<ll> ans ;
 
      for(ll i=0 ; i<m ; ++i)
      {
        ll x;
        cin>>x;
 
        auto lb = ms.lower_bound(x);
        auto ub = ms.upper_bound(x);
        if(*lb==*ub  && ub==ms.begin())
        {
          ans.push_back(-1);
          continue;
        }
        if(*lb==x)
        {
          ans.push_back(x);
          ms.erase(lb);
          continue;
        }
        if(*ub==x)
        {
          ans.push_back(x);
          ms.erase(ub);
          continue;
        }
        --ub ;
        if(*ub>x)
        {
          ans.push_back(-1);
          continue;
        }
        if(*ub<=x)
        {
          ans.push_back(*ub);
          ms.erase(ub);
          continue;
        }
      }
      for(auto i : ans)
        cout<<i<<"\n";
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
        5 3
        5 3 7 8 5
        4 8 3
        
        3
        8
        -1
 
        
 
   */
   ```
   
   ### approach 2 (better)
   
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
      ll n,m ;
      cin>>n>>m;

      multiset<ll,greater<ll>> ms;

      for(ll i=0 ; i<n ; ++i)
      {
        ll x;
        cin>>x;
        ms.insert(x);
      }

      vector<ll> ans;
      for(ll i=0 ; i<m ; ++i)
      {
        ll x;
        cin>>x;
        auto it=ms.lower_bound(x);
        if(it==ms.end())
        {
          ans.push_back(-1);
          continue;
        }
        else
        {
          ans.push_back(*it);
          ms.erase(it);
        }
      }
      for(auto i : ans)
        cout<<i<<"\n";

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
        5 3
        5 3 7 8 5
        4 8 3
        
        3
        8
        -1
 
        
 
   */
   ```
   
   
   ### 21)  Restaurent Customers
   
   assign customers coming to restaurent as 1's and leaving as -1's store them in pairs with thier visiting times , sort the vector wrt. visiting times , problem reduces to finding max. prefix sum 
   
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

   bool comp(pair<ll,ll> &a , pair<ll,ll> &b)
   {
      return a.first < b.first ;
   }
    
   void solve()
   {
      ll n;
      cin>>n ;

      vector< pair<ll,ll> > a ;

      for(ll i=0 ; i<n ; ++i)
      {
        ll x,y;
        cin>>x>>y; 
        a.push_back(make_pair(x,1));
        a.push_back(make_pair(y,-1));
      }

      sort(a.begin(),a.end());
      ll csum=0;
      ll ans=0;

      for(auto i : a)
      {
        csum+=i.second;
        ans=max(ans,csum);
      }
      cout<<ans;

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
   ## Day 4
   
   ### 22) Movie Festival 
   
   you sort the the start and end times w.r.t thier end times , and ofcourse you watch the first movie , you watch every next movie only when it starts after the previous movie watched
   
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

   bool comp(pair<ll,ll> &a , pair<ll,ll> &b)
   {
    return a.second<b.second ;
   }
    
   void solve()
   {
      ll n ;
      cin>>n ;

      vector< pair<ll,ll> > a;

      for(ll i=0 ; i<n ; ++i)
      {
        ll x,y;
        cin>>x>>y;
        a.push_back(make_pair(x,y));
      }

      sort(a.begin(),a.end(),comp);

      ll ans=1;

      ll endtime=a[0].second ;

      for(ll i=1 ; i<n ; ++i)
      {
        if(a[i].first>=endtime)
        {
          ++ans;
          endtime=a[i].second;
        }
      }

      cout<<ans;


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
   
   ### 23) Sum of Two Values 
   
   problem looks very simple and easy at first glance , but isn't that simple  
   
   idea is to store indices of elements in a map 
   
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
      ll n,k ;
      cin>>n>>k;

      map<ll,ll> mp ;
      vector<ll> a(n) ;

      for(ll i=0 ; i<n ; ++i)
      {
        cin>>a[i];
        mp[a[i]]=i;
      }
      bool found=false;
      for(ll i=0  ; i<n ; ++i)
      {
        if(mp.find(k-a[i])!=mp.end() && mp[k-a[i]]!=i)
        {
          found=true;
          cout<<i+1<<" "<<mp[k-a[i]]+1<<"\n";
          return ;
        }
      }

      if(!found)
        cout<<"IMPOSSIBLE";

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
   
   ### 24) Maximum Subarray Sum
   
   keep track of max. current sum ,at each point find maximum of the cmax's 
   
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
      cin>>n;
      vector<ll> a(n) ;
      for(ll i=0 ; i<n ; ++i)
        cin>>a[i] ;

      ll cmax=0;
      ll ans=-INF ;
      for(ll i=0 ; i<n ; ++i)
      {
        cmax=max(a[i],cmax+a[i]);
        ans=max(ans,cmax);
      }
      cout<<ans;

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
   
   ### 25) Stick Lengths
   
   sort the stick lengths , cut them w.r.t the middle stick
   
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
      vector<ll> a(n);

      for(ll i=0 ; i<n ; ++i)
        cin>>a[i];

      sort(a.begin(), a.end());

      ll tocm ;

      tocm=a[n/2];

      ll ans=0;

      for(ll i=0 ; i<n ; ++i)
        ans+=abs(tocm-a[i]);
      cout<<ans;


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
   ## Day 5 (skipped)
   
   ## Day 6
   
   ### 26)  Playlist 
   
   the trick is to store indices of elements as map values , and finding length of sequence using two pointers l and r (r-l+1) ,whenever we encounter i'th element repeating we change l to mp[i]+1 , we also make sure the repeated value's map value to be greater than mp[i] ,
   
   ```cpp
   #include<bits/stdc++.h> 
#include<chrono>
   using namespace std; 
   using namespace std::chrono; 
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

  vector<ll> a(n);

  for(ll i=0 ; i<n ; ++i)
    cin>>a[i];

  map<ll,ll> mp ;
    
  ll accept=0;
  ll ans=-INF ;
      
  for(ll i=0 ; i<n ; ++i)
  {
    if(mp.find(a[i])!=mp.end() && mp[a[i]]>=accept)
    {
      accept=mp[a[i]]+1;
      mp.at(a[i])=i;
    }
    else
    {
      mp[a[i]]=i;
    }
    ans=max(ans,i-accept+1);
  }
  cout<<ans;

}

int main()
{
  inputoutput();
  int t=1;
  // cin>>t;
  while(t--)
    solve();
}
```

   ### 27) Towers 
   
   because we need to use all cubes and we cannot place first cube onto any other cube we start making a tower of first cube  , from there on if we find cube greater than or equal to any other previous cubes , we obviosly need another tower , if the new cube is smaller than maxsize cube , we place on top of upper_bound of this's cube's size and update its value to new cube ( by erasing and adding another element )  , all this is done by using multiset 
   
   #### to delete one element from set/multiset we could use "find" like this 
   
   ```txt
   auto it = s.upper_bound(a[i]);
      auto it2=s.find(*it);
      s.erase(it2);
  ```
  
  
      
   
   ```cpp
   #include<bits/stdc++.h> 
#include<chrono>
   using namespace std; 
   using namespace std::chrono; 
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
  cin>>n ;

  vector<ll> a(n);

  for(ll i=0 ; i<n ; ++i)
    cin>>a[i];

  multiset<ll> s;
  s.insert(a[0]);
  ll ans=1 ;

  for(ll i=1 ; i<n ; ++i)
  {
    if(a[i]>=*s.rbegin())
    {
      ++ans;
      s.insert(a[i]);
    }
    else
    {
      auto it = s.upper_bound(a[i]);
      auto it2=s.find(*it);
      s.erase(it2);
      s.insert(a[i]);
    }
  }
  cout<<ans;

}

int main()
{
  inputoutput();
  int t=1;
  // cin>>t;
  while(t--)
    solve();
}

/*
    5
    3 8 2 1 5

    3 8 9 12 16 17  20 50   13

    upper bound 





*/
```

### 28) Traffic lights 

maintain a set of all points (n)  , initially insert 0 and x , because these are initial points , and keep inserting them when points arrive , whats also important is to maintain , another multiset to store length of segments , initially its only x , as points arrive , we know that some some segments are going to be divided  , so ,  find these segments from the set of points and delete the length of segment from multiset , and add new segments to multiset , use "*ms.rbegin()" to find max length segment so far

```cpp
#include<bits/stdc++.h> 
using namespace std; 
#define deb(x) cout <<"\n"<< (#x) << " = " << (x) << "\n"
const long long  INF = 1e18;
const long long mod=1e9+7 ;
#define ll long long 


void solve()
{
    ll x,n;
    cin>>x>>n;

    set<ll> points = {0,x};
    multiset<ll> length ={x} ; // lengths of segments

    vector<ll> ans ;

    for(ll i=0 ; i<n ; ++i)
    {
      ll point ;
      cin>>point ;
      // find right place to insert this point 
      auto it = points.upper_bound(point);

      int left,right ; // range 

      left=*prev(it);
      right=*it ;

      // first erase this existing segment

      length.erase(length.find(right-left));

      // now insert new ranges 

      length.insert(point-left);
      length.insert(right-point);

      // now print max of all lengths

      // insert new point 

      points.insert(point);

      ans.push_back(*length.rbegin());

    }

    for(auto i : ans)
      cout<<i<<" ";
  
}

int main()
{
  ios_base::sync_with_stdio(0);
  cin.tie(0);
  int t=1;
  // cin>>t;
  while(t--)
    solve();
}

/*

*/
```

### 29) Counting Rooms 

dfs on every .'s , use a vis array to keep track of visited rooms , and find number of connected components

```cpp
#include<bits/stdc++.h> 
using namespace std; 
#define deb(x) cout <<"\n"<< (#x) << " = " << (x) << "\n"
const long long  INF = 1e18;
const long long mod=1e9+7 ;
#define ll long long 


int n,m;
char ar[1000][1000];
int dx[]={-1,0,1,0};
int dy[]={0,1,0,-1};
bool vis[1000][1000];

bool legal(int x,int y)
{
  if(x<0 || x>=n || y<0 || y>=m)
    return false;
  return true;
}

void dfs(int x,int y)
{
  vis[x][y]=true;
  for(int i=0 ; i<4 ; ++i)
  {
    int nx=x+dx[i];
    int ny=y+dy[i];
    if(legal(nx,ny))
    {
      if(vis[nx][ny])
        continue;
      if(ar[nx][ny]=='#')
        continue;
      dfs(nx,ny);
    }
  }
}

void solve()
{
  memset(vis,false,sizeof(vis));

  cin>>n>>m;
  for(int i=0 ; i<n ; ++i)
  {
    for(int j=0 ; j<m ; ++j)
      cin>>ar[i][j];
  }

  int ans=0;

  for(int i=0 ; i<n ; ++i)
  {
    for(int j=0 ; j<m ; ++j)
    {
      if(ar[i][j]=='.' && !vis[i][j])
      {
        dfs(i,j);
        ++ans;
      }
    }
  }
  cout<<ans<<"\n" ;
}

int main()
{
  ios_base::sync_with_stdio(0);
  cin.tie(0);
  int t=1;
  // cin>>t;
  while(t--)
    solve();
}

/*

*/
```

### 30) Labyrinth 

used bfs in this  

```cpp
#include<bits/stdc++.h> 
using namespace std; 
#define deb(x) cout <<"\n"<< (#x) << " = " << (x) << "\n"
const long long  INF = 1e18;
const long long mod=1e9+7 ;
#define ll long long 

int n,m;
char ar[1000][1000];
queue< pair<int,int> > q;
int dx[]={-1,0,1,0};
int dy[]={0,1,0,-1};
bool vis[1000][1000];
int p[1000][1000];

bool legal(int x,int y)
{
  if(x<0 || x>=n || y<0 || y>=m)
    return false;
  return true;
}

void bfs(int x,int y)
{
  q.push(make_pair(x,y));
  vis[x][y]=true;

  while(!q.empty())
  {
    int vx=q.front().first;
    int vy=q.front().second;
    q.pop();

    for(int i=0 ; i<4 ; ++i)
    {
      int nx=vx+dx[i];
      int ny=vy+dy[i];
      if(!legal(nx,ny))
        continue;
      if(vis[nx][ny])
        continue;
      if(ar[nx][ny]=='#')
        continue;
      vis[nx][ny]=true;
      p[nx][ny]=i;
      q.push(make_pair(nx,ny));
    }
  }
}

void solve()
{
  memset(vis,false,sizeof(vis));
  cin>>n>>m ;
  pair<int,int> begin ;
  pair<int,int> end ;

  for(int i=0 ; i<n ; ++i)
  {
    for(int j=0 ; j<m ; ++j)
    {
      cin>>ar[i][j];
      if(ar[i][j]=='A')
        begin=make_pair(i,j);
      else if(ar[i][j]=='B')
        end=make_pair(i,j);
    }
  }


  bfs(begin.first,begin.second);

  if(!vis[end.first][end.second])
    cout<<"NO\n";
  else
  {
    string path ;
    cout<<"YES\n";
    while(end!=begin)
    {
      int k=p[end.first][end.second];
      if(k==0)
        path.push_back('U');
      else if(k==1)
        path.push_back('R');
      else if(k==2)
        path.push_back('D');
      else
        path.push_back('L');
      end=make_pair(end.first-dx[k],end.second-dy[k]);
    }
    reverse(path.begin(), path.end());
    cout<<path.size()<<"\n";
    cout<<path<<"\n";
  }

}

int main()
{
  ios_base::sync_with_stdio(0);
  cin.tie(0);
  int t=1;
  // cin>>t;
  while(t--)
    solve();
}

/*

*/
```

### 31) Building Roads 

finding number of connected components , ans is comp-1 , 

```cpp
#include<bits/stdc++.h> 
using namespace std; 
#define deb(x) cout <<"\n"<< (#x) << " = " << (x) << "\n"
const long long  INF = 1e18;
const long long mod=1e9+7 ;
#define ll long long 

ll n,m;
vector<ll> adj[100500];
bool vis[100500];

void dfs(ll x)
{
  vis[x]=true;
  for(auto u :  adj[x])
  {
    if(!vis[u])
      dfs(u);
  }
}

void solve()
{
  memset(vis,false,sizeof(vis));
  cin>>n>>m ;
  for(ll i=0 ; i<m ; ++i)
  {
    ll x,y;
    cin>>x>>y;
    adj[x].push_back(y);
    adj[y].push_back(x);
  }
  ll ans=0;
  vector< pair<ll,ll> > vp ;
  vector<ll> res ;

  for(ll i=1 ; i<=n ; ++i)
  {
    if(!vis[i])
    {
      if(res.size()%2==0)
        res.push_back(i);
      else
      {
        res.push_back(i);
        res.push_back(i);
      }
      dfs(i);
      ++ans;
    }
  }
  cout<<ans-1<<"\n";

  for(ll i=0 ; i<res.size()-1 ; i+=2)
    cout<<res[i]<<" "<<res[i+1]<<"\n";
}

int main()
{
  ios_base::sync_with_stdio(0);
  cin.tie(0);
  int t=1;
  // cin>>t;
  while(t--)
    solve();
}

/*

*/
```

### 32) Message Routes

simple bfs on 1 works for this 

```cpp
#include<bits/stdc++.h> 
using namespace std; 
#define deb(x) cout <<"\n"<< (#x) << " = " << (x) << "\n"
const long long  INF = 1e18;
const long long mod=1e9+7 ;
#define ll long long 

int n,m ;
vector<int> adj[100500];
bool vis[100500];
vector<int> p(100500);
queue<int> q;

void bfs(int x)
{
  vis[x]=true;
  q.push(x);
  p[x]=-1;
  while(!q.empty())
  {
    int v=q.front();
    q.pop();

    for(auto u: adj[v])
    {
      if(!vis[u])
      {
        vis[u]=true;
        q.push(u);
        p[u]=v;
      }
    }
  }
}

void solve()
{
  cin>>n>>m;
  for(int i=0 ; i<m ; ++i)
  {
    int a,b;
    cin>>a>>b;
    adj[a].push_back(b);
    adj[b].push_back(a);
  }
      bfs(1);

  if(!vis[n])
  {
    cout<<"IMPOSSIBLE\n";
    return ;
  }    
      vector<int> steps ;


  for(int v=n ; v!=-1 ; v=p[v])
    steps.push_back(v);
  reverse(steps.begin(), steps.end());
  cout<<steps.size()<<"\n";
  for(auto i  :steps)
    cout<<i<<" ";

}

int main()
{
  ios_base::sync_with_stdio(0);
  cin.tie(0);
  int t=1;
  // cin>>t;
  while(t--)
    solve();
}

/*

*/
```

## Enough of CSES , now will be uploading Useful Algo's Learned during practice : 

### finding max-length subarry such that the sum of subarray is <=t ( not 100 % sure this algo works or not , but this worked in codeforces 279B Books )

```cpp
#include<bits/stdc++.h> 
using namespace std; 
#define deb(x) cout <<"\n"<< (#x) << " = " << (x) << "\n"
const long long  INF = 1e18;
const long long mod=1e9+7 ;
#define ll long long 

ll n,t;

void solve()
{
	cin>>n>>t;

	vector<ll> a(n);

	for(ll i=0 ; i<n ; ++i)
		cin>>a[i];

	ll cmax=0;
	ll ans=-INF;
	ll len=0;
	ll k=0;

	for(ll i=0 ; i<n ; ++i)
	{
		cmax+=a[i];
		if(cmax>t)
		{
			cmax=cmax-a[k++];
			ans=max(ans,len);
			--len;
		}
		++len;
	}
	ans=max(ans,len);

	cout<<ans<<"\n";

}

int main()
{
  ios_base::sync_with_stdio(0);
  cin.tie(0);
  int t=1;
  // cin>>t;
  while(t--)
    solve();
}



/*
	2 10
	6 4	

*/
```

### CSES DP-1 Dice Combinations 

explanation in code...

```cpp
	#include<bits/stdc++.h> 
using namespace std; 
#define deb(x) cout <<"\n"<< (#x) << " = " << (x) << "\n"
const long long  INF = 1e18;
const long long mod=1e9+7 ;
#define ll long long 


void solve()
{
	int n;
	cin>>n ;

	/* 	f(n)=no. of ways of making sum n using dice
		
		if I know no. of ways to make sum n-1 = f(n-1)

		if f(n-1) is known/computed 
		first I bring sum (n-1) using f(n-1) ways 
		then I can get sum n using dice sided 1 to 
		make sum n

		similary if I know f(n-2) I can always bring 
		dice sided 2 to bring sum n

		hence , 

		f(n)=f(n-1)+f(n-2)+f(n-3)+f(n-4)+f(n-5)+f(n-6)

		for smaller values sometimes f(n-k) doesn't 
		exist , we don't need to add that

		base case : f(0)=1 
	*/

	vector<int> dp(n+1,0);
	dp[0]=1;

	for(int i=1 ; i<n+1 ; ++i)
	{
		for(int j=1 ; j<=6 ; ++j)
		{
			if(i-j<0)
				break;
			dp[i]=(dp[i]+dp[i-j])%mod;
		}
	}
	cout<<dp[n]<<"\n";

}

int main()
{
  ios_base::sync_with_stdio(0);
  cin.tie(0);
  int t=1;
  // cin>>t;
  while(t--)
    solve();
}
/*
		n=7
		3 ince 
		3 dec

		* * * * * * *

		
*/
```

### CSES MINIMIZING COINS 

```cpp

#include<bits/stdc++.h> 
using namespace std; 
#define deb(x) cout <<"\n"<< (#x) << " = " << (x) << "\n"
const long long  INF = 1e18;
const long long mod=1e9+7 ;
#define ll long long 

/*
	given n,x 
	and array of length n consisting of coin types

	we have to make sum x using min. no. of coins from 
	the given coins and print min. no of coins reqd , if 
	not possible to make sum print -1 

	to make sum x , we can choose different subsets from
	array to make sum x

	f(x)=min. no. of coins reqd to make sum x using 
		coin values 
	we have n coins for this purpose 
	
	we have to make sum x
	Lets consider coin 1 
	with value coin[1] 

	I know I am using this coin 1 so ans is already 1
	beacuse I have used it 
	now I need to know what is the minimum no. of coins
	required to make sum (x-coin[1])

	I can do the same with coin 2 (with val coin[2])

	or with all other coins

	of course I want minimum of all those ansers

	so 

	f(x)=min(1+f(x-coin[1]),1+f(x-coin[2]),1+f(x-coin[3]))	
	............ up to n

	also 
	base case : 
	f(0)=minimum no. of coins required to make sum 0
	using coins which is 0
	f(0)=0 ;

*/

void solve()
{
	ll n,x;
	cin>>n>>x;

	vector<ll> a(n);
	for(ll i=0 ; i<n ; ++i)
		cin>>a[i];

	vector<ll> dp(x+1,INF);
	
	dp[0]=0;

	for(ll i=1 ; i<x+1 ; ++i)
	{
		for(ll j=0 ; j<n ; ++j)
		{
			if(i-a[j]<0)
				continue;
			dp[i]=min(dp[i],1+dp[i-a[j]]);
		}
	}	
	if(dp[x]==INF)
		cout<<"-1\n";
	else
	cout<<dp[x]<<"\n";	

}

int main()
{
  ios_base::sync_with_stdio(0);
  cin.tie(0);
  int t=1;
  // cin>>t;
  while(t--)
    solve();
}
/*
		n=7
		3 ince 
		3 dec

		* * * * * * *

		
*/
```

### CSES Coin Combination 1

```cpp
#include<bits/stdc++.h> 
using namespace std; 
#define deb(x) cout <<"\n"<< (#x) << " = " << (x) << "\n"
const long long  INF = 1e18;
const long long mod=1e9+7 ;
#define ll long long 

/*
	given n,x 
	and array of length n consisting of coin types

	we have to find out how many ways can we make sum
	x using coin values given

	f(x)=no. of ways of making sum x using available coins
	
	again consider a first coin 1
	with value coin[1]

	If i use this coin and know no. of ways of making
	coin x-coin[1] this is part of ans 

	similarly for all distinct coin values

	f(x)=f(x-coin[1])+f(x-coin[2])+f(x-coin[3])..upto n

	base case : 
	f(0)=1 
	no. of ways to make sum 0 is 1

*/

void solve()
{
	ll n,x;
	cin>>n>>x;

	vector<ll> a(n);

	for(ll i=0 ; i<n ; ++i)
		cin>>a[i];

	vector<ll> dp(x+1,0);

	dp[0]=1 ;

	for(ll i=1 ; i<x+1 ; ++i)
	{
		for(ll j=0 ; j<n ; ++j)
		{
			if(i-a[j]<0)
				continue;
			dp[i]=(dp[i]%mod+dp[i-a[j]]%mod);
		}
	}
	cout<<dp[x]<<"\n";		

}

int main()
{
  ios_base::sync_with_stdio(0);
  cin.tie(0);
  int t=1;
  // cin>>t;
  while(t--)
    solve();
}
/*
		n=7
		3 ince 
		3 dec

		* * * * * * *

		
*/
```

### CSES Coin Combination 2 
```cpp
#include<bits/stdc++.h> 
using namespace std; 
#define deb(x) cout <<"\n"<< (#x) << " = " << (x) << "\n"
const long long  INF = 1e18;
const long long mod=1e9+7 ;
#define ll long long 

/*
	given n,x 
	and array of length n consisting of coin types

	task is to find no. of distict ordered ways to 
	produce sum x using given coin values

	the difference between this problem and the 
	previous being the order of the coin doesn't matter

	that is 
	for sum x=9

	2+2+5 and
	2+5+2 are counted same

	0 1 2 3 4 5 6 7 8 9 10 11 12 13 14

2	1 0 1 0 1 0 1 0 1 0 1  0  1  0  1
3   1 0 1 1 1 1 2 1 2 2 2  2  3  2  3
5   1 0 1 1 1 2 2 2 3 3 4

	ok , so...

	because order of the sum doesnt matter

	for the first coin we go through dp array and see
	what are the no. of ways of making this sum dp[i]
	using only coin coin[1]

	and we update dp array like this 
	next we go for the next coin (coin[2])

	now we find what are the no. of ways of making this 
	sum dp[i] using coin coin[2] and we keep updating dp
	array

	so.. instead of for each sum dp[i] going through all
	coins gives sometimes different permutations ,
	but ,
	for each coin going through all dp[i] ,
	makes sure we don't encounter different permutations
	choosing the coins orderly


*/

void solve()
{
	ll n,x;
	cin>>n>>x ;

	vector<ll> a(n);

	for(ll i=0 ; i<n ; ++i)
		cin>>a[i];

	vector<ll> dp(x+1,0);

	dp[0]=1;

	for(ll i=0 ; i<n ; ++i)
	{
		for(ll j=1 ; j<x+1 ; ++j)
		{
			if(j-a[i]<0)
				continue;
			dp[j]=(dp[j]+dp[j-a[i]])%mod;
		}
	}
	cout<<dp[x]<<"\n";

}

int main()
{
  ios_base::sync_with_stdio(0);
  cin.tie(0);
  int t=1;
  // cin>>t;
  while(t--)
    solve();
}
/*
		
*/
```

### CSES Removing Digits 

doesn't need much explaination after the previos explanations

```cpp
#include<bits/stdc++.h> 
using namespace std; 
#define deb(x) cout <<"\n"<< (#x) << " = " << (x) << "\n"
const long long  INF = 1e18;
const long long mod=1e9+7 ;
#define ll long long 

/*
	u are given an integer n. On each step, you may 
	substract from it any one-digit number that appears 
	in it.
	How many steps are required to make the number equal
	 to 0?


	f(n)=min. no of steps reqd to make n to 0 , on 
	each step substracting any one digit

	for the first number we have 
	no. of digits in n options 

	f(n)=1+min(n-dig1,n-dig2,n-dig3.....)

	also 
	f(0)=0 (0 steps)


*/

void solve()
{
	ll n;
	cin>>n;

	vector<ll> dp(n+1,INF);

	dp[0]=0;

	for(ll i=1 ; i<n+1 ; ++i)
	{
		vector<ll> digits ;
		ll temp=i;
		while(temp!=0)
		{
			digits.push_back(temp%10);
			temp/=10;
		}
		for(ll j=0 ; j<digits.size() ; ++j)
		{
			if(i-digits[j]<0)
				continue;
			if(digits[j]!=0)
			dp[i]=min(dp[i],1+dp[i-digits[j]]);
		}
	}
	cout<<dp[n]<<"\n";

}

int main()
{
  ios_base::sync_with_stdio(0);
  cin.tie(0);
  int t=1;
  // cin>>t;
  while(t--)
    solve();
}
/*
		
*/
```

### CSES GRID PATHS

```cpp
   #include<bits/stdc++.h> 
using namespace std; 
#define deb(x) cout <<"\n"<< (#x) << " = " << (x) << "\n"
const long long  INF = 1e18;
const long long mod=1e9+7 ;
#define ll long long 

/*
	no_of_paths(1,1,n,n)=no_of_paths(1,2,n,n)+
						 no_of_paths(2,1,n,n)

*/

void solve()
{
	ll n;
	cin>>n;

	char a[n][n];	
	for(ll i=0 ; i<n;  ++i)
	{
		for(ll j=0 ; j<n ; ++j)
			cin>>a[i][j];
	}

	ll dp[n][n];
	memset(dp,0,sizeof(dp));

	dp[n-1][n-1]=1 ;

	if(a[n-1][n-1]=='*' || a[0][0]=='*')
	{
		cout<<"0\n";
		return; 
	}

	for(ll i=n-2 ; i>=0 ; --i)
	{
		if(a[n-1][i]!='*')
			dp[n-1][i]+=dp[n-1][i+1];
	}
	for(ll i=n-2 ; i>=0 ; --i)
	{
		if(a[i][n-1]!='*')
			dp[i][n-1]+=dp[i+1][n-1];
	}

	for(ll i=n-2 ; i>=0 ; --i)
	{
		for(ll j=n-2 ; j>=0 ; --j)
		{
			if(a[i][j]!='*')
			{
				dp[i][j]=(dp[i+1][j]%mod+dp[i][j+1]%mod)%mod;
			}
		}
	}


	cout<<dp[0][0]<<"\n";
}

int main()
{
  ios_base::sync_with_stdio(0);
  cin.tie(0);
  int t=1;
  // cin>>t;
  while(t--)
    solve();
}
/*
		
*/
```

### CSES Book Shop 

similar to 0-1 knacksap 

```cpp
#include<bits/stdc++.h> 
using namespace std; 
#define deb(x) cout <<"\n"<< (#x) << " = " << (x) << "\n"
const long long  INF = 1e18;
const long long mod=1e9+7 ;
#define ll long long 

/*			

*/

void solve()
{
	int n,x;
	cin>>n>>x;

	vector<int> price(n),pages(n);

	for(int i=0 ; i<n ; ++i)
		cin>>price[i];
	for(int i=0 ; i<n ; ++i)
		cin>>pages[i];

	vector< vector<int> > dp(n+1,vector<int>(x+1,0));

	for(int i=1 ; i<=n ; ++i)
	{
		for(int j=0 ; j<=x ; ++j)
		{
			dp[i][j]=dp[i-1][j];
			int left=j-price[i-1];
			if(left>=0)
			{
				dp[i][j]=max(dp[i][j],pages[i-1]+dp[i-1][left]);
			}
		}
	}
	cout<<dp[n][x]<<"\n";

}

int main()
{
  ios_base::sync_with_stdio(0);
  cin.tie(0);
  int t=1;
  // cin>>t;
  while(t--)
    solve();
}
/*
		
*/
```

   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   

