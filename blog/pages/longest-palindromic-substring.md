- 5
- Given a string `s`, return the longest palindromic substring in `s`.
-
- ```
  class Solution {
      public String longestPalindrome(String s) {
          int l = 0, r = 0, len = s.length();
          char[] ss = s.toCharArray();
          for(int i = 0; i < len; i++) {
              int max = Math.max(helper(ss, i, i), helper(ss, i, i + 1));
              if(max > r - l + 1) {
                  l = i - max / 2 + (max % 2 == 0 ? 1 : 0);
                  r = i + max / 2;
              }
          }
          return s.substring(l, r + 1);
      }
      private int helper(char[] s, int l, int r) {
          while(l >= 0 && r < s.length && s[l] == s[r]) {
              l--;
              r++;
          }
          return r - l - 1;
      }
  }
  ```
- [[leetcode]] [[String]] [[Two Pointers]]
-