# Daily-DSA-Problem
Day 1
House Robber(Classic Dp problem)
public int robbed(int[] nums){
      int i=0;
      int n= nums.length;
      int free = 1;
      int[][] dp = new int[n][2];
      for(int[] row: dp){
          Arrays.fill(row,-1);
        }
      return fun(i,free,n,nums,dp);
    }
    static int fun(int i,int free,,int n ,int[] nums, int[][] dp){
         if(i==n){
         return 0;
         } 
      if(dp[i][free]!=-1){
         return dp[i][free];
         }
         if(free==0){
          return dp[i][free] = fun(i+1,1,n,nums,dp);
          }
          int c1 = nums[i] + fun(i+1,0,n,nums,dp);
          int c2 = fun(i+1,1,n,nums,dp);
          int ans = Math.max(c1,c2);
          dp[i][free]= ans;
          return ans;
          }
