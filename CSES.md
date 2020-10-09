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
   
   requires observation , we have two cases y>x or x>y   , then we find the max element that possibly could be in that row (squared observation) 
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
   
   ### 15) Apartments 
   
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
   
   ### 16)
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   

