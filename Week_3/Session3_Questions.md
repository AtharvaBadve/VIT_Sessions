# Session 3 · Part 1 — Questions

Interview Readiness Program. Eight problems: two carried over as homework from Session 2, four solved in class, two assigned as homework.

---

## Homework review (from Session 2)

### HW 1 · Shortest subarray with sum ≥ K

Given an integer array `a` and a positive `K`, return the length of the shortest non-empty contiguous subarray whose sum is at least `K`.

Values may be negative. Return `−1` if no such subarray exists.

**Constraints**
- 1 ≤ n ≤ 100,000; 1 ≤ K ≤ 10⁹
- Values are integers within ±10⁹.
- Return a length, not the sum or the indices.

**Examples**
```
a = [2,-1,2,-1,2,3], K = 5   →  2
a = [1,-1,1],        K = 4   →  -1
```
In the first case the final `[2,3]` has sum 5 and length 2; no single value reaches 5. In the second, no contiguous subarray reaches 4.

---

### HW 2 · Smaller values to the right

Given an integer array `a`, return an array `ans` of the same length. For each position `i`, `ans[i]` counts the positions `j > i` where `a[j]` is strictly less than `a[i]`.

Count each occurrence separately. Equal values do not count.

**Constraints**
- 0 ≤ n ≤ 100,000; values within ±10⁹
- Return counts in the original input order.
- For an empty array, return an empty array.

**Examples**
```
a = [5,2,6,1,2]  →  [3,1,2,0,0]
a = [2,2]        →  [0,0]
```
For 5 the smaller values to its right are 2, 1, 2. For the first 2, only 1. For 6, both 1 and 2. The final 1 and 2 have nothing smaller after them. In `[2,2]`, equality counts neither.

---

## In-class problems

### Question 1 · Largest rectangle in a histogram

Given bar heights, each of width 1, return the area of the largest rectangle that fits entirely inside the histogram.

The rectangle must be axis-aligned and rest on the baseline.

**Constraints**
- 1 ≤ n ≤ 100,000; 0 ≤ height ≤ 10⁹
- Return the area, not the bars.
- A single bar is a valid rectangle.

**Examples**
```
[2,1,5,6,2,3]  →  10     tall and narrow: two neighbours of height ≥ 5
[4,2,3,2,5,1]  →  10     short and wide: height 2 across five bars, taller bars in between
```

---

### Question 2 · Decode a nested string

An encoded string uses the rule `k[s]`, meaning the string `s` is repeated exactly `k` times. Encodings can be nested.

Return the decoded string.

**Constraints**
- 1 ≤ length ≤ 30; `k` is a positive integer, possibly multi-digit.
- Input is always valid: brackets are balanced.
- Letters are lowercase; no digits appear outside a count.
- Output length is at most 10⁵.

**Examples**
```
s = "3[a2[c]]"       →  "accaccacc"
s = "2[abc]3[cd]ef"  →  "abcabccdcdcdef"
```
In the first case the inner `2[c]` becomes `cc`, so the outer bracket holds `acc`, repeated 3 times. In the second, two groups are decoded in sequence and `ef` is appended as-is.

---

### Question 3 · Rotting oranges

A grid holds empty cells (`0`), fresh oranges (`1`) and rotten oranges (`2`). Every minute, each rotten orange rots the fresh oranges directly above, below, left and right of it.

Return the number of minutes until no fresh orange remains, or `−1` if that never happens.

**Constraints**
- 1 ≤ rows, cols ≤ 10; cells are 0, 1 or 2
- Rotting spreads to all four neighbours at once.
- If there are no fresh oranges to begin with, answer 0.

**Examples**
```
[[2,1,1],          [[2,1,1],
 [1,1,0],    → 4    [0,1,1],    → -1
 [0,1,1]]           [1,0,1]]
```
Left: rot spreads one ring per minute and reaches the far corner in 4. Right: the orange at the bottom-left is walled off by empty cells, so it never rots.

---

### Question 4 · Minimum meeting rooms

You are given meetings as `[start, end)` intervals. Return the minimum number of rooms needed so that no two meetings that overlap in time share a room.

A meeting that ends at time `t` and one that starts at time `t` may use the same room.

**Constraints**
- 1 ≤ n ≤ 10⁴; 0 ≤ start < end ≤ 10⁶
- Meetings are not given in any order.
- Return a single integer: the number of rooms.

**Examples**
```
[[0,30],[5,10],[15,20]]     →  2
[[1,5],[2,6],[3,7],[4,8]]   →  4
```
First case: `[5,10]` and `[15,20]` can share a room, `[0,30]` needs its own. Second: all four meetings overlap at time 4, so four rooms.

---

## Homework · Part 1

Both go to your GitHub repository before the next session, with a time-and-space complexity comment at the top of each file. Also code every in-class problem.

### Q1 · Evaluate an expression

A string with non-negative integers, `+ − × ÷`, parentheses and spaces. Return its value. Usual precedence; integer division truncates toward zero.

**Constraints**
- 1 ≤ length ≤ 10⁵; the result fits in 32 bits.
- The input is always a valid expression.

**Examples**
```
"3 + 5 * (2 - 8)"         →  -27
"10 / 2 - 3"              →  2
"(1+(4+5+2)-3)+(6+8)"     →  23
```
*Hint:* Two kinds of unfinished work: numbers waiting for an operator, and operators waiting until precedence lets them run. Where does each kind wait?

---

### Q2 · Trapping rain water

Bars of width 1 with the given heights. After it rains, how many units of water are held between them?

**Constraints**
- 1 ≤ n ≤ 20,000; 0 ≤ height ≤ 10⁵
- The first and last bars never hold water.

**Examples**
```
[0,1,0,2,1,0,1,3,2,1,2,1]  →  6
[4,2,0,3,2,5]              →  9
```
*Hint:* Which bar closes a pool, and how far back does that pool reach? You have solved a close relative of this today.
