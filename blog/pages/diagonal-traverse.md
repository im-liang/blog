- 498
- Given an `m x n` matrix `mat`, return *an array of all the elements of the array in a diagonal order*.
- **Input:** mat = \[[1,2,3],[4,5,6],[7,8,9]]
  **Output:** [1,2,4,7,5,3,6,8,9]
-
- ```
  class Solution {
      public int[] findDiagonalOrder(int[][] mat) {
          int row = mat.length, col = mat[0].length;
          int[] res = new int[row * col];
          int ptr = 0;
          int[] pos = new int[] {0, 0};
          while(ptr < res.length) {
              res[ptr++] = mat[pos[0]][pos[1]];
              pos = next(mat, pos);
          }
          return res;
      }
  
      private int[] next(int[][] mat, int[] pos) {
          int x = pos[0], y = pos[1];
          int row = mat.length, col = mat[0].length;
          if(x == row - 1 && y == col - 1) return new int[] {-1, -1};
          if((x + y) % 2 == 0) {
              if(y + 1 == col) return new int[] {x + 1, y};
              if(x == 0) return new int[] {x, y + 1};
              return new int[] {x - 1, y + 1};
          }else {
              if(x == row - 1) return new int[] {x, y + 1};
              if(y == 0) return new int[] {x + 1, y};
              return new int[] {x + 1, y - 1};
          }
      }
  }
  ```
- [[leetcode]] [[Array]]