
DFS PATTERN 

1 . NUMBER OF ISLANDS 

MISTAKE I DID :
I FORGOT TO CHECK BOUNDARY CONDN
- Changed `if (grid[nr][nr] != '1')` to verify the neighbor cell is valid via `if (nr >= 0 && nr < m && nc >= 0 && nc < n && grid[nr][nc] == '1')`.

i was also confused that hould i make a new grid 2d array nd pass it or original one

ANS === Modifying the **original grid** in place is the preferred and most efficient approach for this problem

**Saves Space**: Creating a new 2D array or a `visited` tracking matrix takes \(O(M \times N)\) extra memory. Modifying the original grid drops your auxiliary space complexity to O(1) (excluding the recursive call stack



How to Use a Separate Matrix (If Required)

If an interviewer explicitly asks you **not** to mutate the input data, use a 2D boolean array named `visited` instead of creating a whole new grid copy.

```
// Inside numIslands:
int m = grid.size();
int n = grid[0].size();
vector<vector<bool>> visited(m, vector<bool>(n, false));

// Inside your loops:
if (grid[i][j] == '1' && !visited[i][j]) {
    dfs(i, j, grid, visited);
    count++;
}

// Inside your DFS function:
visited[r][c] = true;
// When checking neighbors, ensure: !visited[nr][nc]

```

It actually **can** come up in normal LeetCode questions or interviews, and interviewers use it as a trick question.

Many interviewers will watch you write the in-place solution first. Once you finish, they will often ask a follow-up question: _"This works great, but what if the grid is read-only or we need to preserve the original data for another part of our application?"

Strategy 1: The "Restore" Trick (Best for O(1) Space)

Instead of allocating a giant new matrix, you can modify the grid during the DFS, and then **change it back** before the function exits.

1. Flip `'1'` to a temporary marker like `'X'` during DFS.
2. After counting all islands, run a quick loop over the grid to change all `'X'` characters back to `'1'`.
3. This keeps your extra space complexity at O(1) while keeping the interviewer happy.

```
class Solution {
public:
    int dx[4] = {-1, 0, 1, 0};
    int dy[4] = {0, 1, 0, -1};

    void dfs(int r, int c, vector<vector<char>>& grid) {
        int m = grid.size();
        int n = grid[0].size();
        
        // Mark as visited using a temporary placeholder
        grid[r][c] = 'X'; 
        
        for (int i = 0; i < 4; i++) {
            int nr = dx[i] + r;
            int nc = dy[i] + c;
            
            // Only traverse if it is unvisited land ('1')
            if (nr >= 0 && nr < m && nc >= 0 && nc < n && grid[nr][nc] == '1') {
                dfs(nr, nc, grid);
            }
        }
    }

    int numIslands(vector<vector<char>>& grid) {
        if (grid.empty()) return 0;
        
        int m = grid.size();
        int n = grid[0].size();
        int count = 0;
        
        // Step 1: Count islands and mark them as 'X'
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (grid[i][j] == '1') {
                    dfs(i, j, grid);
                    count++;
                }
            }
        }
        
        // Step 2: Restore the original grid data
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (grid[i][j] == 'X') {
                    grid[i][j] = '1';
                }
            }
        }
        
        return count;
    }
};

```

Strategy 2: The `visited` Matrix

If the interviewer says the grid is strictly **read-only** (e.g., passed as `const vector<vector<char>>& grid`), you cannot use the restore trick. You must use the `visited` matrix approach shown previously.

Pro-Tip for Interviews

Always ask the interviewer this clarifying question before writing code for grid problems:

> _"Is it okay if I modify the input grid directly to save space, or should I treat it as immutable_???





