# RS-Activity-CPS-Assignment-01

#Problem 1:   
a. Time complexity is O(nlogn)
  Outer loop O(n/2) or O(n)
  For the inner loop the loop can run as long as 2^k <= n . If we solve the value of k then , k = logn.
  Now, the combined time complexity will be O(nlogn)

b. The time complexity of this is O(sqrt(n))
  The while loop starts with i = 1 and increments i until i * i exceeds n.
  This means the loop runs approximately until i*i <= n.
  The number of iterations is roughly sqrt(n)
​  as i increases linearly and stops when i * i surpasses n.

2.
```
class Solution {
    public int maxArea(int[] height) {
        int ans = 0;

        int l = 0; int r = height.length - 1;
        ArrayList<Integer> kek = new ArrayList<Integer>();
        for(int i = 0; i < height.length; i++){
            kek.add(height[i]);
        }
        while(l < r){
            if(Math.min(kek.get(l), kek.get(r)) * (r-l) > ans){
                ans = Math.min(kek.get(l), kek.get(r))* (r-l);
            }
            if(kek.get(l) > kek.get(r)){
                r--;
            }
            else{
                l++;
            }
        }
        return ans;
    }
}
```
This code finds the maximum area of water trapped between two vertical lines using the two-pointer approach in O(n) time complexity.

  Initialize Two Pointers:
        l at the leftmost index (0).
        r at the rightmost index (height.length - 1).

  Iterate While l < r:
        Compute the area: min(kek.get(l), kek.get(r)) * (r - l).
        Update ans if this area is larger.
        Move the pointer pointing to the smaller height inward to maximize potential height gain.

  Efficiency:
        Avoids brute-force O(n²) checking by using O(n) two-pointer traversal.
        Uses constant extra space, but the ArrayList<Integer> kek is unnecessary and can be replaced with height.

Final Complexity: O(n) time complexity

