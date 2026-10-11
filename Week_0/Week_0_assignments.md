# Session 1 — Assignment 1

Deadline: before the next session.

## Q1 · Complexity analysis of searching & sorting algorithms

For each algorithm, write the best / average / worst case time (and the input that causes each), space (including the recursion stack), whether it is stable and in-place, and one line on why. Also give quick sort as O / Ω / Θ. Push as `notes/complexity.md`.

- [ ] Bubble sort
- [ ] Insertion sort
- [ ] Selection sort
- [ ] Merge sort
- [ ] Quick sort (+ O / Ω / Θ)
- [ ] Linear search
- [ ] Binary search

## Q2 · Implement `vector` from scratch

`template <typename T> class Vector` — data pointer, size, capacity around one contiguous heap block.

- [ ] `push_back` / `pop_back`, doubling capacity when full
- [ ] `operator[]` and bounds-checked `at()`
- [ ] `size()`, `capacity()`, `empty()`, `reserve()`, `resize()`, `clear()`
- [ ] `begin()` / `end()`
- [ ] Rule of five (destructor, copy, move) — no leaks
- [ ] Tests with `harness.hpp`; complexity of each operation in a comment

## Q3 · Implement a 2D vector from scratch

`template <typename T> class Matrix` — one flat block, row-major: element (i, j) at `data[i * cols + j]`.

- [ ] Constructor `(rows, cols, fill)`, `rows()`, `cols()`
- [ ] `operator()(i, j)` or `m[i][j]`, bounds-checked `at(i, j)`
- [ ] `fill()`, `resize(rows, cols)`
- [ ] Rule of five, or build on Q2's `Vector<T>`
- [ ] Compare with `Vector<Vector<T>>`: are rows contiguous? how many allocations?
- [ ] Time summing a large matrix `i`-outer vs `j`-outer — which is faster, and why?
