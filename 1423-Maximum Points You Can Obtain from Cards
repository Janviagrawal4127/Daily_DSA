class Solution {
    public int maxScore(int[] cardPoints, int k) {
       int n = cardPoints.length;

       int rSum=0;
       int lSum=0;
       int maxSum=0;

       for(int i =0; i<=k-1;i++)
       {
        lSum += cardPoints[i];
       } 
       maxSum = lSum;

       int r = n-1;

       for(int i = k-1; i>=0; i--)
       {

        lSum -= cardPoints[i];
        rSum += cardPoints[r];


        maxSum = Math.max(maxSum , lSum+rSum);

        r--;
       }

        return maxSum;
    }
}
