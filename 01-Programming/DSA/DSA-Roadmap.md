# DSA Master Roadmap v2

> **Cách dùng file này**
> - Cú pháp `[[...]]` là wikilink Obsidian. Mỗi bài = 1 note.
> - 🟢 Easy · 🟡 Medium · 🔴 Hard
> - `⭐` = bài đại diện pattern. **Bắt buộc** làm, phải tự viết lại được từ đầu sau 3 ngày.
> - `🔒` = bài LeetCode Premium. Tôi có ghi bài thay thế miễn phí ngay bên dưới.
> - Mỗi pattern có mục **🔍 Nhận diện** (dấu hiệu trong đề bài) và **⏱ Mục tiêu** (độ phức tạp cần đạt). Đọc hai mục này trước khi làm bài.

---

## ⚠️ Về độ tin cậy của danh sách

Tôi nhận diện pattern và nhớ nội dung các bài LeetCode phổ biến khá chính xác, nhưng không truy cập LeetCode trực tiếp khi lập danh sách. Vì vậy:

- Các bài kinh điển (số hiệu < 1000, Blind 75, NeetCode 150) gần như chắc chắn đúng.
- Các bài số hiệu > 1500 có rủi ro nhỏ về sai lệch số hiệu. **Tìm theo TÊN bài trên LeetCode thay vì theo số** nếu link không khớp.
- LeetCode thỉnh thoảng đổi tên bài (ví dụ bài 28 đã đổi tên ít nhất 2 lần).
- Danh sách này đủ để đi phỏng vấn. Nhưng "không cần làm bài ở chỗ khác" chỉ đúng nếu bạn làm đủ số bài `⭐` và làm thêm **contest hàng tuần** để rèn tốc độ dưới áp lực. Đọc/làm đúng danh sách ≠ phản xạ tốt trong 45 phút phỏng vấn.

---
---

# 🧭 BẢNG NHẬN DIỆN PATTERN

Bảng này quan trọng hơn cả danh sách bài. In ra, dán lên tường.

| Dấu hiệu trong đề bài | Pattern nên nghĩ tới ngay |
|---|---|
| Mảng **đã sắp xếp**, tìm cặp/bộ ba | Two Pointers đối đầu |
| Mảng đã sắp xếp, tìm 1 giá trị / vị trí | Binary Search |
| "Subarray / substring **liên tiếp**" | Sliding Window |
| "Subarray liên tiếp" + có số âm | Prefix Sum + HashMap |
| "Tất cả subset / hoán vị / tổ hợp" | Backtracking |
| "Đếm số cách" / "có bao nhiêu cách" | DP |
| "Tối ưu (min/max)" + có lựa chọn rời rạc | DP hoặc Greedy |
| "Top K" / "K lớn nhất" | Heap (size K) hoặc Quickselect |
| "Median của luồng dữ liệu" | Two Heaps |
| "Minimum của maximum" / "maximum của minimum" | **Binary Search on Answer** |
| "Phần tử lớn hơn tiếp theo" / "gần nhất bên trái/phải" | **Monotonic Stack** |
| Max/min trong cửa sổ trượt | Monotonic Deque |
| Ma trận + lan tỏa / vùng liên thông | DFS / BFS trên grid |
| "Đường đi ngắn nhất", cạnh không trọng số | BFS |
| "Đường đi ngắn nhất", cạnh có trọng số dương | Dijkstra |
| Có trọng số âm / giới hạn số cạnh | Bellman-Ford |
| "Thứ tự thực hiện", "điều kiện tiên quyết" | Topological Sort |
| "Nhóm / gộp / cùng một nhóm" động | Union-Find |
| "Nối tất cả với chi phí nhỏ nhất" | MST (Prim / Kruskal) |
| Prefix của chuỗi, autocomplete | Trie |
| "Khoảng", "lịch họp", "chồng lấn" | Intervals / Sweep Line |
| XOR, "xuất hiện 1 lần", n ≤ 20 | Bit Manipulation / Bitmask DP |
| Linked list + "chu trình" / "giữa" | Fast & Slow Pointers |
| Cần O(1) get + O(1) put | HashMap + Doubly Linked List |
| Range query + có update | Fenwick / Segment Tree |
| Range query + không update | Prefix Sum |
| n ≤ 20 | Bitmask / brute force 2^n |
| n ≤ 100–500 | O(n³) chấp nhận được, nghĩ DP 2D |
| n ≤ 10^5 | Cần O(n log n) |
| n ≤ 10^7 | Cần O(n) |

---
---

# 📅 LỘ TRÌNH HỌC (bản đã hiệu chỉnh)

### Thay đổi so với bản trước
1. Giai đoạn nền tảng giãn từ 2 → 3 tuần. Bản cũ nhồi Big-O + Dynamic Array + Hash Implementation + Sorting + Recursion vào 2 tuần, quá tải cho người mới.
2. Thêm **checkpoint** cuối mỗi giai đoạn: tự kiểm tra bằng 3 bài random chưa từng gặp, bấm giờ 45 phút. Không đạt thì ôn lại, không đi tiếp.
3. Thêm **sơ đồ phụ thuộc** để bạn biết cái gì bắt buộc học trước cái gì.
4. Thêm nhánh **Fast Track 8 tuần** cho người sắp phỏng vấn.
5. Thêm 2 tuần cuối dành riêng cho mock interview và ôn tập, thay vì kết thúc ngay sau phần nâng cao.

### Sơ đồ phụ thuộc

```
Big-O ──> Arrays & Hashing ──> Two Pointers ──> Sliding Window
   │              │
   │              └──> Prefix Sum ──> Fenwick/Segment Tree
   │
   ├──> Sorting ──> Binary Search ──> Binary Search on Answer
   │
   ├──> Stack ──> Monotonic Stack
   │        └──> Queue/Deque ──> Monotonic Deque
   │
   └──> Recursion ──┬──> Trees (DFS) ──> BST ──> Tree DP
                    │         └──> BFS ──> Graph BFS
                    ├──> Backtracking ──> Trie ──> Bit Trie
                    └──> DP 1D ──> DP 2D ──> Knapsack ──> Bitmask/Interval DP

Heap ──> Top-K, Two Heaps ──> Dijkstra / Prim
Union-Find ──> Kruskal
Graph DFS/BFS ──> Topo Sort ──> Advanced Graphs
```

### Cấu trúc một buổi học (90–120 phút)

| Thời lượng | Việc |
|---|---|
| 10 phút | Ôn lại bài `⭐` của hôm trước, **không nhìn code cũ** |
| 15 phút | Đọc lý thuyết pattern mới + vẽ tay ví dụ nhỏ |
| 50 phút | Làm 2–3 bài mới (tối đa 20 phút/bài, hết giờ thì xem lời giải) |
| 20 phút | Code lại bài vừa xem lời giải, **không nhìn** |
| 10 phút | Viết note: nhận diện được từ dấu hiệu nào, lỗi mình mắc |

---

### 📑 Index theo tuần — mở section nào vào tuần nào

File này sắp xếp theo **chủ đề** để tra cứu. Lộ trình đi theo **độ khó tăng dần**. Hai trục đó không trùng nhau ở vài chỗ, nên dùng bảng này làm cầu nối. Mỗi section trong file đều có nhãn `📅 Tuần ...` ngay dưới tiêu đề.

| Tuần | Section cần mở |
|---|---|
| 1 | Arrays & Hashing (Dynamic Arrays → Hash Usage) · JavaScript (viết template) |
| 2 | Arrays & Hashing (Prefix Sums, Difference Array) · Sorting |
| 3 | Recursion & Divide and Conquer · Two Pointers |
| 4 | Sliding Window (trừ Monotonic Deque) |
| 5 | Stack |
| 6 | Queue & Deque · Monotonic Deque |
| 7 | Binary Search |
| 8 | Linked List · Design |
| 9–10 | Trees |
| 11 | Heap / Priority Queue |
| 12–13 | Backtracking · Tries |
| 14–15 | Graphs |
| 16 | Advanced Graphs (bỏ qua SCC/Bridges/Eulerian) |
| 17–18 | 1-D Dynamic Programming |
| 19 | 2-D Dynamic Programming (bỏ qua Interval DP, Bitmask DP, Digit DP) |
| 20 | Greedy · Intervals · Math & Geometry · Bit Manipulation |
| 21 | Interval DP · Bitmask DP · Digit DP · SCC/Bridges/Eulerian · Segment Tree & Fenwick · String Algorithms |
| 22–23 | Không mở section mới. Mock interview + ôn bài ⭐ |

> Các mục đánh dấu `⏭ Tuần 21` nằm rải trong file thuộc Giai đoạn 7. Khi học lần đầu thì **bỏ qua**, quay lại sau.

## Giai đoạn 0 — Nền tảng (Tuần 1–3)

| Tuần | Mở section | Sản phẩm phải có |
|---|---|---|
| 1 | Big-O · **Arrays & Hashing** (Dynamic Arrays, Hash Implementation, Hash Usage) | Tự cài `DynamicArray` và `HashMap` bằng chaining |
| 2 | **Arrays & Hashing** (Prefix Sums, Difference Array) · **Sorting** (cả 5 nhóm) | Tự cài merge sort + quick sort không nhìn tài liệu |
| 3 | **Recursion & Divide and Conquer** · **Two Pointers** (cả 4 nhóm) | Vẽ được recursion tree cho bài 509 và 50 |

**Checkpoint 0**: giải được 217, 1, 238, 560, 912, 215 trong 60 phút tổng.

## Giai đoạn 1 — Pattern lõi (Tuần 4–8)
80% câu hỏi phỏng vấn thực tế nằm ở đây.

| Tuần | Mở section |
|---|---|
| 4 | **Sliding Window** (fixed, variable, `atMost(k) - atMost(k-1)`) — bỏ qua Monotonic Deque, để tuần 6 |
| 5 | **Stack** (cả 4 nhóm, Monotonic Stack là phần nặng nhất) |
| 6 | **Queue & Deque** + quay lại làm Monotonic Deque ở cuối section Sliding Window |
| 7 | **Binary Search** (cả 3 nhóm, gồm Binary Search on Answer) |
| 8 | **Linked List** (3 nhóm) → **Design** (LRU cần Doubly Linked List nên phải học sau) |

**Checkpoint 1**: giải 3, 424, 739, 33, 875, 143 trong 90 phút. Đây là mức đủ để pass vòng phone screen của phần lớn công ty.

## Giai đoạn 2 — Cây & Heap (Tuần 9–11)

| Tuần | Chủ đề |
|---|---|
| 9 | Binary Tree DFS (traversal, đệ quy có trả về giá trị), BFS theo tầng |
| 10 | BST: insert/remove/validate/iterator, Iterative DFS, LCA, Serialize, Tree DP |
| 11 | Heap: tự cài MinHeap + heapify, Top-K, Merge-K, Two Heaps |

**Checkpoint 2**: giải 124, 98, 297, 295 trong 90 phút.

## Giai đoạn 3 — Backtracking & Trie (Tuần 12–13)

| Tuần | Chủ đề |
|---|---|
| 12 | Subsets → Combinations → Permutations (đúng thứ tự này), Partition |
| 13 | Grid backtracking, Constraint pruning (N-Queens, Sudoku), Trie + Bit Trie |

**Checkpoint 3**: giải 90, 40, 47, 79, 212 trong 100 phút.

## Giai đoạn 4 — Đồ thị (Tuần 14–16)

| Tuần | Chủ đề |
|---|---|
| 14 | Matrix DFS/BFS, Flood Fill, Multi-source BFS, BFS có state |
| 15 | Adjacency List, Cycle Detection, Bipartite, Union-Find, Topological Sort |
| 16 | Dijkstra, Bellman-Ford, Floyd-Warshall, Prim, Kruskal |

**Checkpoint 4**: giải 417, 207, 684, 743, 787 trong 100 phút.

## Giai đoạn 5 — Quy hoạch động (Tuần 17–19)
Mỗi bài DP đi đúng 4 bước: **đệ quy thuần → memo → tabulation → tối ưu bộ nhớ**. Bỏ bước nào cũng sẽ hổng.

| Tuần | Chủ đề |
|---|---|
| 17 | 1-D DP: Climbing Stairs, House Robber, Coin Change, Word Break, Decode Ways |
| 18 | Palindromes, LIS, State Machine (Stock series), Jump Game |
| 19 | 2-D DP: Grid path, LCS, Edit Distance, 0/1 & Unbounded Knapsack |

**Checkpoint 5**: giải 322, 300, 309, 72, 416 trong 100 phút.

## Giai đoạn 6 — Bổ trợ (Tuần 20)

| Chủ đề |
|---|
| Greedy + Kadane + Exchange Argument |
| Intervals + Sweep Line + Difference Array |
| Math & Geometry (Sieve, GCD, fast pow, Fisher-Yates) |
| Bit Manipulation (XOR tricks, bitmask enumeration) |

## Giai đoạn 7 — Nâng cao (Tuần 21, tùy chọn)

Chỉ làm nếu nhắm FAANG/quant hoặc thi competitive. Không cần cho phần lớn phỏng vấn product company.

| Chủ đề |
|---|
| Interval DP, Bitmask DP |
| Fenwick Tree / Segment Tree |
| KMP, Rabin-Karp, Z-function |
| SCC (Tarjan), Bridges, Eulerian Path |

## Giai đoạn 8 — Luyện phỏng vấn (Tuần 22–23)

| Việc | Tần suất |
|---|---|
| Mock interview có bấm giờ, **nói ra miệng** | 3 buổi/tuần |
| LeetCode Weekly Contest | 1 lần/tuần, làm nghiêm túc |
| Ôn lại toàn bộ bài `⭐` đã đánh dấu sai | Hằng ngày |
| Luyện giải thích độ phức tạp + trade-off | Mỗi bài |

---

## 🚀 Fast Track — 8 tuần (khi đã có deadline phỏng vấn)

Chỉ làm các bài `⭐`, bỏ qua mọi thứ đánh dấu Giai đoạn 7.

| Tuần | Chủ đề |
|---|---|
| 1 | Arrays & Hashing, Prefix Sum, Two Pointers |
| 2 | Sliding Window, Stack + Monotonic Stack |
| 3 | Binary Search + Binary Search on Answer, Linked List |
| 4 | Trees (DFS, BFS, BST) |
| 5 | Heap, Backtracking, Trie |
| 6 | Graphs (DFS/BFS, Topo, Union-Find, Dijkstra) |
| 7 | DP 1D + 2D + Knapsack |
| 8 | Greedy, Intervals, Bit + mock interview mỗi ngày |

---

## 🔁 Quy tắc ôn tập

1. **Spaced repetition**: bài sai → làm lại sau 1 ngày → 3 ngày → 7 ngày → 21 ngày.
2. **20 phút rule**: bí quá 20 phút thì đọc lời giải, nhưng **đóng lại và tự code từ đầu ngay**. Hôm sau code lại lần nữa.
3. Mỗi note ghi đủ 5 mục: *Dấu hiệu nhận diện* · *Ý tưởng 1 câu* · *Code* · *Độ phức tạp* · *Lỗi mình mắc*.
4. Từ Giai đoạn 2 trở đi: mỗi tuần 1 mock interview 45 phút, nói to ý tưởng trước khi gõ code.
5. **Không đọc lời giải trước khi tự nghĩ ít nhất 10 phút.** Đọc sớm tạo cảm giác hiểu bài giả.

---
---

# **Arrays & Hashing**
> 📅 **Tuần 1–2** · Giai đoạn 0

### Dynamic Arrays
🔍 Nhận diện: thao tác tại chỗ trên mảng, "in-place", "O(1) extra space".
⏱ Mục tiêu: O(n) time, O(1) space.

1. [[1929. Concatenation of Array]] 🟢
2. [[1299. Replace Elements with Greatest Element on Right Side]] 🟢 ⭐ (duyệt từ phải sang)
3. [[27. Remove Element]] 🟢
4. [[26. Remove Duplicates from Sorted Array]] 🟢 ⭐
5. [[80. Remove Duplicates from Sorted Array II]] 🟡
6. [[88. Merge Sorted Array]] 🟢 ⭐ (ghi từ cuối về đầu)
7. [[283. Move Zeroes]] 🟢
8. [[448. Find All Numbers Disappeared in an Array]] 🟢
9. [[485. Max Consecutive Ones]] 🟢
10. [[1051. Height Checker]] 🟢
11. [[189. Rotate Array]] 🟡 (kỹ thuật reverse 3 lần)
12. [[724. Find Pivot Index]] 🟢

### Hash Implementation
🔍 Nhận diện: đề yêu cầu "design", không cho dùng thư viện có sẵn.
⏱ Mục tiêu: O(1) trung bình.

1. [[705. Design HashSet]] 🟢 ⭐ (separate chaining)
2. [[706. Design HashMap]] 🟢 ⭐ (open addressing, so sánh 2 cách)

### Hash Usage
🔍 Nhận diện: "duplicate", "anagram", "đếm tần suất", "tìm cặp có tổng bằng", cần tra cứu O(1).
⏱ Mục tiêu: đổi O(n²) thành O(n) bằng cách đánh đổi bộ nhớ.

1. [[217. Contains Duplicate]] 🟢
2. [[242. Valid Anagram]] 🟢
3. [[1. Two Sum]] 🟢 ⭐
4. [[383. Ransom Note]] 🟢
5. [[205. Isomorphic Strings]] 🟢
6. [[290. Word Pattern]] 🟢
7. [[49. Group Anagrams]] 🟡 ⭐
8. [[347. Top K Frequent Elements]] 🟡 ⭐ (bucket sort, không dùng heap)
9. [[271. Encode and Decode Strings]] 🟡 🔒 → thay bằng [[443. String Compression]] 🟡
10. [[128. Longest Consecutive Sequence]] 🟡 ⭐
11. [[36. Valid Sudoku]] 🟡
12. [[454. 4Sum II]] 🟡 ⭐ (chia đôi, meet in the middle)
13. [[1657. Determine if Two Strings Are Close]] 🟡
14. [[2352. Equal Row and Column Pairs]] 🟡

### Prefix Sums
🔍 Nhận diện: hỏi tổng/XOR/tích trên nhiều đoạn con, hỏi nhiều lần; có số âm nên sliding window không dùng được.
⏱ Mục tiêu: tiền xử lý O(n), mỗi query O(1).

1. [[303. Range Sum Query - Immutable]] 🟢 ⭐
2. [[724. Find Pivot Index]] 🟢
3. [[1732. Find the Highest Altitude]] 🟢
4. [[238. Product of Array Except Self]] 🟡 ⭐ (prefix × suffix)
5. [[304. Range Sum Query 2D - Immutable]] 🟡 ⭐ (prefix 2 chiều)
6. [[560. Subarray Sum Equals K]] 🟡 ⭐ (prefix + HashMap, bài quan trọng nhất nhóm này)
7. [[525. Contiguous Array]] 🟡 ⭐ (map 0 → -1)
8. [[974. Subarray Sums Divisible by K]] 🟡 (prefix mod)
9. [[523. Continuous Subarray Sum]] 🟡
10. [[1310. XOR Queries of a Subarray]] 🟡
11. [[930. Binary Subarrays With Sum]] 🟡
12. [[1248. Count Number of Nice Subarrays]] 🟡
13. [[2270. Number of Ways to Split Array]] 🟢

### Difference Array 🆕
🔍 Nhận diện: nhiều lệnh "cộng thêm v vào đoạn [l, r]", chỉ hỏi kết quả cuối.
⏱ Mục tiêu: mỗi update O(1), tổng hợp O(n).

1. [[1109. Corporate Flight Bookings]] 🟡 ⭐
2. [[1094. Car Pooling]] 🟡 ⭐
3. [[370. Range Addition]] 🟡 🔒 → thay bằng [[2381. Shifting Letters II]] 🟡

---

# **Sorting**
> 📅 **Tuần 2** · Giai đoạn 0

### Comparison Sorts
🔍 Nhận diện: đề yêu cầu tự cài, hoặc cần sort ổn định, hoặc sort linked list.
⏱ Mục tiêu: O(n log n).

1. [[912. Sort an Array]] 🟡 ⭐ (cài cả Merge Sort và Quick Sort)
2. [[148. Sort List]] 🟡 ⭐ (merge sort trên linked list, O(1) space với bottom-up)
3. [[147. Insertion Sort List]] 🟡
4. [[88. Merge Sorted Array]] 🟢
5. [[21. Merge Two Sorted Lists]] 🟢

### Non-comparison Sorts
🔍 Nhận diện: giá trị nằm trong khoảng hẹp đã biết (0..k), hoặc cần phá cận O(n log n).
⏱ Mục tiêu: O(n + k).

1. [[75. Sort Colors]] 🟡 ⭐ (Dutch National Flag, 3-way partition)
2. [[1122. Relative Sort Array]] 🟢 ⭐ (counting sort)
3. [[451. Sort Characters By Frequency]] 🟡 (bucket sort)
4. [[347. Top K Frequent Elements]] 🟡 (bucket sort)
5. [[164. Maximum Gap]] 🔴 (bucket / radix sort)

### Cyclic Sort
🔍 Nhận diện: mảng chứa n số trong khoảng [1..n] hoặc [0..n], tìm số thiếu/trùng, yêu cầu O(1) space.
⏱ Mục tiêu: O(n) time, O(1) space.

1. [[268. Missing Number]] 🟢 ⭐
2. [[448. Find All Numbers Disappeared in an Array]] 🟢
3. [[442. Find All Duplicates in an Array]] 🟡 ⭐
4. [[287. Find the Duplicate Number]] 🟡
5. [[41. First Missing Positive]] 🔴 ⭐
6. [[645. Set Mismatch]] 🟢

### Quickselect
🔍 Nhận diện: "phần tử thứ K", chỉ cần K chứ không cần sort toàn bộ.
⏱ Mục tiêu: O(n) trung bình.

1. [[215. Kth Largest Element in an Array]] 🟡 ⭐
2. [[973. K Closest Points to Origin]] 🟡 ⭐
3. [[347. Top K Frequent Elements]] 🟡
4. [[692. Top K Frequent Words]] 🟡

### Custom Comparator
🔍 Nhận diện: cần định nghĩa thứ tự riêng, sort theo nhiều tiêu chí.

1. [[179. Largest Number]] 🟡 ⭐ (so sánh `b+a` vs `a+b`)
2. [[1029. Two City Scheduling]] 🟡 ⭐
3. [[937. Reorder Data in Log Files]] 🟡
4. [[506. Relative Ranks]] 🟢
5. [[1636. Sort Array by Increasing Frequency]] 🟢

---

# **Recursion & Divide and Conquer**
> 📅 **Tuần 3** · Giai đoạn 0

🔍 Nhận diện: bài toán tự chia thành bài con cùng dạng; "chia đôi"; cây đệ quy.
⏱ Mục tiêu: hiểu Master Theorem ở mức T(n) = 2T(n/2) + O(n) → O(n log n).

1. [[509. Fibonacci Number]] 🟢 ⭐ (naive → memo → iterative, vẽ recursion tree)
2. [[70. Climbing Stairs]] 🟢
3. [[344. Reverse String]] 🟢 (bản đệ quy)
4. [[206. Reverse Linked List]] 🟢 ⭐ (bản đệ quy)
5. [[50. Pow(x, n)]] 🟡 ⭐ (fast exponentiation, xử lý n âm)
6. [[241. Different Ways to Add Parentheses]] 🟡 ⭐
7. [[95. Unique Binary Search Trees II]] 🟡
8. [[23. Merge k Sorted Lists]] 🔴 ⭐ (D&C, so sánh với heap)
9. [[53. Maximum Subarray]] 🟡 (bản D&C, so sánh với Kadane)
10. [[169. Majority Element]] 🟢 (bản D&C và bản Boyer-Moore)
11. [[427. Construct Quad Tree]] 🟡

---

# **Two Pointers**
> 📅 **Tuần 3** · Giai đoạn 0

### Opposite Direction (hai đầu tiến vào giữa)
🔍 Nhận diện: mảng đã sắp xếp, tìm cặp có tổng bằng target, palindrome, diện tích giữa 2 cột.
⏱ Mục tiêu: O(n), thay cho O(n²).

1. [[125. Valid Palindrome]] 🟢 ⭐
2. [[680. Valid Palindrome II]] 🟢 ⭐
3. [[344. Reverse String]] 🟢
4. [[345. Reverse Vowels of a String]] 🟢
5. [[167. Two Sum II - Input Array Is Sorted]] 🟡 ⭐
6. [[11. Container With Most Water]] 🟡 ⭐ (hiểu vì sao dịch cột thấp hơn)
7. [[42. Trapping Rain Water]] 🔴 ⭐ (làm cả 3 cách: prefix max, two pointers, monotonic stack)
8. [[977. Squares of a Sorted Array]] 🟢 ⭐
9. [[881. Boats to Save People]] 🟡
10. [[1750. Minimum Length of String After Deleting Similar Ends]] 🟡

### Same Direction (slow / fast index)
🔍 Nhận diện: lọc/nén mảng tại chỗ, kiểm tra subsequence, ghi đè phần tử hợp lệ.
⏱ Mục tiêu: O(n) time, O(1) space.

1. [[392. Is Subsequence]] 🟢 ⭐
2. [[283. Move Zeroes]] 🟢 ⭐
3. [[26. Remove Duplicates from Sorted Array]] 🟢
4. [[27. Remove Element]] 🟢
5. [[844. Backspace String Compare]] 🟢 ⭐ (bản O(1) space duyệt ngược)
6. [[905. Sort Array By Parity]] 🟢
7. [[443. String Compression]] 🟡
8. [[2109. Adding Spaces to a String]] 🟡

### Three Pointers / k-Sum
🔍 Nhận diện: "bộ ba", "bộ bốn" có tổng bằng target, cần khử trùng lặp.
⏱ Mục tiêu: 3Sum O(n²), 4Sum O(n³).

1. [[15. 3Sum]] 🟡 ⭐ (phần khó nhất là skip duplicate)
2. [[16. 3Sum Closest]] 🟡
3. [[259. 3Sum Smaller]] 🟡 🔒 → thay bằng [[611. Valid Triangle Number]] 🟡
4. [[18. 4Sum]] 🟡
5. [[923. 3Sum With Multiplicity]] 🟡

### Merge Two Sequences
🔍 Nhận diện: hai mảng/danh sách đã sắp xếp, cần gộp hoặc giao.

1. [[88. Merge Sorted Array]] 🟢
2. [[349. Intersection of Two Arrays]] 🟢
3. [[350. Intersection of Two Arrays II]] 🟢
4. [[986. Interval List Intersections]] 🟡 ⭐
5. [[1471. The k Strongest Values in an Array]] 🟡

---

# **Sliding Window**
> 📅 **Tuần 4** · Giai đoạn 1

### Sliding Window Fixed Size
🔍 Nhận diện: "subarray/substring độ dài đúng bằng k".
⏱ Mục tiêu: O(n), cập nhật tăng dần thay vì tính lại cả cửa sổ.

1. [[643. Maximum Average Subarray I]] 🟢 ⭐
2. [[219. Contains Duplicate II]] 🟢
3. [[1876. Substrings of Size Three with Distinct Characters]] 🟢
4. [[567. Permutation in String]] 🟡 ⭐ (so sánh 2 mảng đếm)
5. [[438. Find All Anagrams in a String]] 🟡 ⭐
6. [[2461. Maximum Sum of Distinct Subarrays With Length K]] 🟡
7. [[1456. Maximum Number of Vowels in a Substring of Given Length]] 🟡
8. [[1052. Grumpy Bookstore Owner]] 🟡
9. [[2090. K Radius Subarray Averages]] 🟡

### Sliding Window Variable Size
🔍 Nhận diện: "dài nhất/ngắn nhất thỏa điều kiện", tất cả số **không âm**, đoạn liên tiếp.
⏱ Mục tiêu: O(n), mỗi phần tử vào/ra cửa sổ đúng 1 lần.

1. [[121. Best Time to Buy and Sell Stock]] 🟢 ⭐
2. [[3. Longest Substring Without Repeating Characters]] 🟡 ⭐
3. [[209. Minimum Size Subarray Sum]] 🟡 ⭐
4. [[424. Longest Repeating Character Replacement]] 🟡 ⭐ (mẹo không giảm maxCount)
5. [[1004. Max Consecutive Ones III]] 🟡 ⭐
6. [[904. Fruit Into Baskets]] 🟡
7. [[340. Longest Substring with At Most K Distinct Characters]] 🟡 🔒 → thay bằng [[2024. Maximize the Confusion of an Exam]] 🟡
8. [[76. Minimum Window Substring]] 🔴 ⭐ (bài khó nhất, biến `have/need`)
9. [[239. Sliding Window Maximum]] 🔴 (xem Monotonic Deque)
10. [[1493. Longest Subarray of 1's After Deleting One Element]] 🟡
11. [[713. Subarray Product Less Than K]] 🟡
12. [[2958. Length of Longest Subarray With at Most K Frequency]] 🟡

### Kỹ thuật `atMost(k) - atMost(k-1)` 🆕
🔍 Nhận diện: "đếm số subarray có **đúng** k phần tử phân biệt / đúng k số lẻ".
⏱ Mục tiêu: gọi hàm sliding window 2 lần.

1. [[992. Subarrays with K Different Integers]] 🔴 ⭐
2. [[1248. Count Number of Nice Subarrays]] 🟡 ⭐
3. [[930. Binary Subarrays With Sum]] 🟡

### Monotonic Deque  ·  ⏭ Tuần 6 (học cùng Queue & Deque)
🔍 Nhận diện: cần max/min của cửa sổ trượt, hoặc chênh lệch max-min trong cửa sổ.
⏱ Mục tiêu: O(n) amortized.

1. [[239. Sliding Window Maximum]] 🔴 ⭐
2. [[1438. Longest Continuous Subarray With Absolute Diff Less Than or Equal to Limit]] 🟡 ⭐ (2 deque)
3. [[862. Shortest Subarray with Sum at Least K]] 🔴 (deque + prefix sum, có số âm)
4. [[1696. Jump Game VI]] 🟡 (deque + DP)

---

# **Stack**
> 📅 **Tuần 5** · Giai đoạn 1

### Basic Stack
🔍 Nhận diện: cần khớp cặp, cần undo, "hoàn tác thao tác gần nhất".
⏱ Mục tiêu: O(n).

1. [[20. Valid Parentheses]] 🟢 ⭐
2. [[155. Min Stack]] 🟡 ⭐ (2 stack hoặc lưu cặp)
3. [[682. Baseball Game]] 🟢
4. [[2390. Removing Stars From a String]] 🟡
5. [[1047. Remove All Adjacent Duplicates In String]] 🟢
6. [[1209. Remove All Adjacent Duplicates in String II]] 🟡
7. [[71. Simplify Path]] 🟡 ⭐
8. [[844. Backspace String Compare]] 🟢
9. [[921. Minimum Add to Make Parentheses Valid]] 🟡
10. [[1249. Minimum Remove to Make Valid Parentheses]] 🟡

### Expression Evaluation
🔍 Nhận diện: biểu thức có ngoặc, toán tử, cần tính giá trị hoặc giải mã.

1. [[150. Evaluate Reverse Polish Notation]] 🟡 ⭐
2. [[394. Decode String]] 🟡 ⭐ (2 stack: số và chuỗi)
3. [[227. Basic Calculator II]] 🟡 ⭐
4. [[224. Basic Calculator]] 🔴
5. [[772. Basic Calculator III]] 🔴 🔒
6. [[726. Number of Atoms]] 🔴
7. [[856. Score of Parentheses]] 🟡

### Stack Simulation
🔍 Nhận diện: các phần tử "va chạm", "triệt tiêu" nhau theo thứ tự.

1. [[735. Asteroid Collision]] 🟡 ⭐
2. [[946. Validate Stack Sequences]] 🟡 ⭐
3. [[22. Generate Parentheses]] 🟡
4. [[1441. Build an Array With Stack Operations]] 🟢
5. [[2211. Count Collisions on a Road]] 🟡

### Monotonic Stack ⭐⭐
🔍 Nhận diện: "phần tử **lớn hơn/nhỏ hơn tiếp theo**", "gần nhất bên trái/phải thỏa điều kiện", "diện tích hình chữ nhật lớn nhất", "khoảng mà phần tử này là max/min".
⏱ Mục tiêu: O(n), mỗi phần tử push/pop đúng 1 lần.

1. [[496. Next Greater Element I]] 🟢 ⭐
2. [[739. Daily Temperatures]] 🟡 ⭐ (bài mẫu chuẩn nhất)
3. [[503. Next Greater Element II]] 🟡 ⭐ (mảng vòng, duyệt 2n)
4. [[901. Online Stock Span]] 🟡
5. [[853. Car Fleet]] 🟡 ⭐
6. [[84. Largest Rectangle in Histogram]] 🔴 ⭐ (bài quan trọng nhất nhóm này)
7. [[85. Maximal Rectangle]] 🔴 (84 áp dụng theo từng hàng)
8. [[42. Trapping Rain Water]] 🔴
9. [[402. Remove K Digits]] 🟡 ⭐
10. [[316. Remove Duplicate Letters]] 🟡
11. [[1673. Find the Most Competitive Subsequence]] 🟡
12. [[907. Sum of Subarray Minimums]] 🟡 ⭐ (đếm "khoảng thống trị")
13. [[2104. Sum of Subarray Ranges]] 🟡
14. [[456. 132 Pattern]] 🟡

---

# **Queue & Deque**
> 📅 **Tuần 6** · Giai đoạn 1

🔍 Nhận diện: FIFO, BFS, cần thêm/xóa ở cả hai đầu, buffer vòng.
⏱ Mục tiêu: O(1) mọi thao tác. Trong JS nhớ rằng `Array.shift()` là O(n).

1. [[622. Design Circular Queue]] 🟡 ⭐
2. [[641. Design Circular Deque]] 🟡
3. [[232. Implement Queue using Stacks]] 🟢 ⭐ (amortized O(1))
4. [[225. Implement Stack using Queues]] 🟢
5. [[933. Number of Recent Calls]] 🟢
6. [[346. Moving Average from Data Stream]] 🟢 🔒 → thay bằng [[643. Maximum Average Subarray I]] 🟢
7. [[950. Reveal Cards In Increasing Order]] 🟡
8. [[1823. Find the Winner of the Circular Game]] 🟡 (Josephus)

---

# **Binary Search**
> 📅 **Tuần 7** · Giai đoạn 1

### Search Array
🔍 Nhận diện: mảng đã sắp xếp (kể cả bị xoay), cần O(log n).
⏱ Mục tiêu: O(log n). **Dùng `mid = left + ((right - left) >> 1)`** để tránh tràn số.

1. [[704. Binary Search]] 🟢 ⭐ (thuộc lòng template `while (l <= r)`)
2. [[35. Search Insert Position]] 🟢 ⭐
3. [[278. First Bad Version]] 🟢
4. [[374. Guess Number Higher or Lower]] 🟢
5. [[69. Sqrt(x)]] 🟢
6. [[367. Valid Perfect Square]] 🟢
7. [[74. Search a 2D Matrix]] 🟡 ⭐ (coi ma trận là mảng 1D)
8. [[240. Search a 2D Matrix II]] 🟡 ⭐ (staircase từ góc trên phải, O(m+n))
9. [[33. Search in Rotated Sorted Array]] 🟡 ⭐
10. [[81. Search in Rotated Sorted Array II]] 🟡
11. [[153. Find Minimum in Rotated Sorted Array]] 🟡 ⭐
12. [[154. Find Minimum in Rotated Sorted Array II]] 🔴
13. [[162. Find Peak Element]] 🟡 ⭐
14. [[852. Peak Index in a Mountain Array]] 🟡

### Search Range (lower bound / upper bound)
🔍 Nhận diện: "vị trí đầu tiên/cuối cùng", "số lượng phần tử ≤ x", có phần tử trùng lặp.
⏱ Mục tiêu: O(log n). Viết sẵn 2 hàm `lowerBound` và `upperBound` dùng lại mãi mãi.

1. [[34. Find First and Last Position of Element in Sorted Array]] 🟡 ⭐
2. [[658. Find K Closest Elements]] 🟡 ⭐
3. [[981. Time Based Key-Value Store]] 🟡 ⭐
4. [[1146. Snapshot Array]] 🟡
5. [[528. Random Pick with Weight]] 🟡 ⭐ (prefix sum + upper bound)
6. [[4. Median of Two Sorted Arrays]] 🔴 ⭐ (binary search trên partition)

### Binary Search on Answer ⭐⭐
🔍 Nhận diện: **"minimum của maximum"**, **"maximum của minimum"**, "tốc độ/dung lượng/ngày nhỏ nhất sao cho...". Đáp án nằm trong một khoảng số, và tồn tại hàm `check(x)` đơn điệu (đúng với mọi x ≥ k, sai với mọi x < k).
⏱ Mục tiêu: O(n log(range)). Luôn viết tách hàm `feasible(x)` cho dễ debug.

1. [[875. Koko Eating Bananas]] 🟡 ⭐ (bài mẫu chuẩn nhất)
2. [[1011. Capacity To Ship Packages Within D Days]] 🟡 ⭐
3. [[1482. Minimum Number of Days to Make m Bouquets]] 🟡 ⭐
4. [[410. Split Array Largest Sum]] 🔴 ⭐
5. [[1760. Minimum Limit of Balls in a Bag]] 🟡
6. [[1552. Magnetic Force Between Two Balls]] 🟡 ⭐ (maximize minimum)
7. [[2300. Successful Pairs of Spells and Potions]] 🟡
8. [[1898. Maximum Number of Removable Characters]] 🟡
9. [[1231. Divide Chocolate]] 🔴 🔒 → thay bằng [[1802. Maximum Value at a Given Index in a Bounded Array]] 🟡
10. [[1283. Find the Smallest Divisor Given a Threshold]] 🟡
11. [[2064. Minimized Maximum of Products Distributed to Any Store]] 🟡
12. [[774. Minimize Max Distance to Gas Station]] 🔴 🔒 (binary search trên số thực)

---

# **Linked List**
> 📅 **Tuần 8** · Giai đoạn 1

### Singly Linked Lists
🔍 Nhận diện: cần thao tác con trỏ, không có index. Luôn cân nhắc **dummy head** để xử lý trường hợp xóa node đầu.
⏱ Mục tiêu: O(n) time, O(1) space.

1. [[206. Reverse Linked List]] 🟢 ⭐ (cả iterative và recursive)
2. [[21. Merge Two Sorted Lists]] 🟢 ⭐
3. [[83. Remove Duplicates from Sorted List]] 🟢
4. [[82. Remove Duplicates from Sorted List II]] 🟡
5. [[203. Remove Linked List Elements]] 🟢
6. [[92. Reverse Linked List II]] 🟡 ⭐
7. [[143. Reorder List]] 🟡 ⭐ (kết hợp: tìm giữa + đảo nửa sau + trộn)
8. [[19. Remove Nth Node From End of List]] 🟡 ⭐
9. [[2. Add Two Numbers]] 🟡 ⭐
10. [[445. Add Two Numbers II]] 🟡
11. [[138. Copy List with Random Pointer]] 🟡 ⭐
12. [[61. Rotate List]] 🟡
13. [[86. Partition List]] 🟡
14. [[328. Odd Even Linked List]] 🟡
15. [[25. Reverse Nodes in k-Group]] 🔴 ⭐
16. [[23. Merge k Sorted Lists]] 🔴 ⭐

### Doubly Linked Lists
🔍 Nhận diện: cần xóa node ở vị trí bất kỳ trong O(1), cần LRU/LFU.

1. [[707. Design Linked List]] 🟡 ⭐
2. [[146. LRU Cache]] 🟡 ⭐ (DLL + HashMap, bài design được hỏi nhiều nhất)
3. [[460. LFU Cache]] 🔴
4. [[432. All O`one Data Structure]] 🔴
5. [[1472. Design Browser History]] 🟡 ⭐

### Fast and Slow Pointers
🔍 Nhận diện: "chu trình", "phần tử giữa", "phần tử thứ k từ cuối", yêu cầu O(1) space trên linked list hoặc dãy hàm lặp.
⏱ Mục tiêu: O(n) time, O(1) space.

1. [[876. Middle of the Linked List]] 🟢 ⭐
2. [[141. Linked List Cycle]] 🟢 ⭐
3. [[142. Linked List Cycle II]] 🟡 ⭐ (Floyd's tortoise & hare, chứng minh được công thức)
4. [[202. Happy Number]] 🟢 ⭐
5. [[287. Find the Duplicate Number]] 🟡 ⭐ (áp dụng Floyd lên mảng)
6. [[234. Palindrome Linked List]] 🟢 ⭐
7. [[457. Circular Array Loop]] 🟡
8. [[2095. Delete the Middle Node of a Linked List]] 🟡

---

# **Design / Implement Data Structure**
> 📅 **Tuần 8** · Giai đoạn 1 · cần Linked List và Heap trước

🔍 Nhận diện: đề bắt đầu bằng "Design ...", "Implement ...". Luôn hỏi ngược lại: *thao tác nào cần nhanh nhất?* Rồi chọn cấu trúc theo đó.

1. [[155. Min Stack]] 🟡 ⭐
2. [[146. LRU Cache]] 🟡 ⭐ (được hỏi nhiều nhất trong nhóm này)
3. [[460. LFU Cache]] 🔴
4. [[208. Implement Trie]] 🟡 ⭐
5. [[380. Insert Delete GetRandom O(1)]] 🟡 ⭐ (array + hashmap index)
6. [[295. Find Median from Data Stream]] 🔴 ⭐
7. [[622. Design Circular Queue]] 🟡
8. [[981. Time Based Key-Value Store]] 🟡 ⭐
9. [[355. Design Twitter]] 🟡 ⭐
10. [[1472. Design Browser History]] 🟡
11. [[705. Design HashSet]] / [[706. Design HashMap]] 🟢
12. [[707. Design Linked List]] 🟡
13. [[1396. Design Underground System]] 🟡
14. [[1146. Snapshot Array]] 🟡
15. [[895. Maximum Frequency Stack]] 🔴 ⭐
16. [[1206. Design Skiplist]] 🔴
17. [[642. Design Search Autocomplete System]] 🔴 🔒
18. [[359. Logger Rate Limiter]] 🟢 🔒 → thay bằng [[933. Number of Recent Calls]] 🟢

---

# **Trees**
> 📅 **Tuần 9–10** · Giai đoạn 2

### Depth-First Search
🔍 Nhận diện: bài hỏi về toàn bộ cây con, chiều sâu, đường đi từ gốc. Mẫu chung: hàm đệ quy **trả về thông tin của cây con** và cập nhật biến toàn cục.
⏱ Mục tiêu: O(n) time, O(h) space.

1. [[104. Maximum Depth of Binary Tree]] 🟢 ⭐
2. [[111. Minimum Depth of Binary Tree]] 🟢
3. [[226. Invert Binary Tree]] 🟢 ⭐
4. [[100. Same Tree]] 🟢 ⭐
5. [[101. Symmetric Tree]] 🟢
6. [[572. Subtree of Another Tree]] 🟢 ⭐
7. [[110. Balanced Binary Tree]] 🟢 ⭐ (trả về -1 làm cờ báo lỗi)
8. [[543. Diameter of Binary Tree]] 🟢 ⭐ (mẫu "trả về chiều cao, cập nhật đáp án")
9. [[112. Path Sum]] 🟢
10. [[113. Path Sum II]] 🟡
11. [[437. Path Sum III]] 🟡 ⭐ (prefix sum trên cây)
12. [[124. Binary Tree Maximum Path Sum]] 🔴 ⭐
13. [[687. Longest Univalue Path]] 🟡
14. [[129. Sum Root to Leaf Numbers]] 🟡
15. [[257. Binary Tree Paths]] 🟢
16. [[236. Lowest Common Ancestor of a Binary Tree]] 🟡
17. [[863. All Nodes Distance K in Binary Tree]] 🟡 ⭐ (biến cây thành đồ thị)

### Breadth-First Search
🔍 Nhận diện: "theo tầng", "level", "khoảng cách ngắn nhất từ gốc", "nhìn từ bên phải".
⏱ Mục tiêu: O(n) time, O(w) space với w là độ rộng lớn nhất.

1. [[102. Binary Tree Level Order Traversal]] 🟡 ⭐ (mẫu `for (let i = 0; i < queue.length; i++)`)
2. [[107. Binary Tree Level Order Traversal II]] 🟡
3. [[199. Binary Tree Right Side View]] 🟡 ⭐
4. [[103. Binary Tree Zigzag Level Order Traversal]] 🟡
5. [[515. Find Largest Value in Each Tree Row]] 🟡
6. [[637. Average of Levels in Binary Tree]] 🟢
7. [[1448. Count Good Nodes in Binary Tree]] 🟡
8. [[116. Populating Next Right Pointers in Each Node]] 🟡 ⭐
9. [[117. Populating Next Right Pointers in Each Node II]] 🟡
10. [[662. Maximum Width of Binary Tree]] 🟡 ⭐ (đánh index như heap)
11. [[958. Check Completeness of a Binary Tree]] 🟡

### BST Insert and Remove
🔍 Nhận diện: cây có tính chất trái < gốc < phải, cần chèn/xóa/tìm.
⏱ Mục tiêu: O(h), h = log n nếu cân bằng.

1. [[700. Search in a Binary Search Tree]] 🟢 ⭐
2. [[701. Insert into a Binary Search Tree]] 🟡 ⭐
3. [[450. Delete Node in a BST]] 🟡 ⭐ (3 trường hợp, dùng inorder successor)
4. [[108. Convert Sorted Array to Binary Search Tree]] 🟢 ⭐
5. [[109. Convert Sorted List to Binary Search Tree]] 🟡
6. [[669. Trim a Binary Search Tree]] 🟡
7. [[1008. Construct Binary Search Tree from Preorder Traversal]] 🟡

### BST Sets and Maps
🔍 Nhận diện: cần tận dụng **inorder của BST là dãy tăng dần**.

1. [[98. Validate Binary Search Tree]] 🟡 ⭐ (truyền min/max xuống, không chỉ so với con)
2. [[230. Kth Smallest Element in a BST]] 🟡 ⭐
3. [[938. Range Sum of BST]] 🟢
4. [[235. Lowest Common Ancestor of a Binary Search Tree]] 🟡 ⭐
5. [[530. Minimum Absolute Difference in BST]] 🟢
6. [[501. Find Mode in Binary Search Tree]] 🟢
7. [[1038. Binary Search Tree to Greater Sum Tree]] 🟡 (inorder ngược)
8. [[653. Two Sum IV - Input is a BST]] 🟢
9. [[285. Inorder Successor in BST]] 🟡 🔒 → thay bằng [[510. Inorder Successor in BST II]] 🟡 🔒 → hoặc tự luyện bằng [[173. BST Iterator]]

### Iterative DFS
🔍 Nhận diện: đề cấm đệ quy, hoặc cây quá sâu (stack overflow), hoặc cần iterator.
⏱ Mục tiêu: O(n) time, O(h) space với stack tường minh.

1. [[94. Binary Tree Inorder Traversal]] 🟢 ⭐
2. [[144. Binary Tree Preorder Traversal]] 🟢 ⭐
3. [[145. Binary Tree Postorder Traversal]] 🟢 ⭐ (khó nhất trong 3, dùng mẹo đảo preorder)
4. [[173. Binary Search Tree Iterator]] 🟡 ⭐
5. [[589. N-ary Tree Preorder Traversal]] 🟢
6. [[590. N-ary Tree Postorder Traversal]] 🟢

### Lowest Common Ancestor
🔍 Nhận diện: "tổ tiên chung gần nhất", "khoảng cách giữa 2 node trong cây".

1. [[235. Lowest Common Ancestor of a BST]] 🟡 ⭐
2. [[236. Lowest Common Ancestor of a Binary Tree]] 🟡 ⭐
3. [[1650. Lowest Common Ancestor of a Binary Tree III]] 🟡 🔒 (có parent pointer) → thay bằng [[160. Intersection of Two Linked Lists]] 🟢 (cùng kỹ thuật)
4. [[1123. Lowest Common Ancestor of Deepest Leaves]] 🟡

### Tree Construction & Serialization
🔍 Nhận diện: dựng cây từ các dãy duyệt, lưu/khôi phục cây thành chuỗi.

1. [[105. Construct Binary Tree from Preorder and Inorder Traversal]] 🟡 ⭐
2. [[106. Construct Binary Tree from Inorder and Postorder Traversal]] 🟡
3. [[889. Construct Binary Tree from Preorder and Postorder Traversal]] 🟡
4. [[297. Serialize and Deserialize Binary Tree]] 🔴 ⭐ (preorder + marker null)
5. [[449. Serialize and Deserialize BST]] 🟡
6. [[652. Find Duplicate Subtrees]] 🟡 ⭐ (serialize + hashmap)
7. [[606. Construct String from Binary Tree]] 🟢

### Tree DP
🔍 Nhận diện: "chọn hoặc không chọn node", ràng buộc giữa node cha và con.
⏱ Mục tiêu: O(n), mỗi node trả về một tuple trạng thái.

1. [[337. House Robber III]] 🟡 ⭐ (trả về `[rob, notRob]`)
2. [[124. Binary Tree Maximum Path Sum]] 🔴
3. [[968. Binary Tree Cameras]] 🔴 ⭐ (3 trạng thái)
4. [[979. Distribute Coins in Binary Tree]] 🟡
5. [[834. Sum of Distances in Tree]] 🔴 ⭐ (rerooting technique)
6. [[543. Diameter of Binary Tree]] 🟢

### N-ary & Special Trees 🆕
1. [[559. Maximum Depth of N-ary Tree]] 🟢
2. [[429. N-ary Tree Level Order Traversal]] 🟡
3. [[1522. Diameter of N-Ary Tree]] 🟡 🔒
4. [[1490. Clone N-ary Tree]] 🟡 🔒 → thay bằng [[133. Clone Graph]] 🟡

---

# **Heap / Priority Queue**
> 📅 **Tuần 11** · Giai đoạn 2

### Heap Properties, Push và Pop
🔍 Nhận diện: cần lấy min/max liên tục khi dữ liệu thay đổi.
⏱ Mục tiêu: push/pop O(log n), peek O(1). **JS không có sẵn, phải tự cài.**

1. [[703. Kth Largest Element in a Stream]] 🟢 ⭐
2. [[1046. Last Stone Weight]] 🟢 ⭐
3. [[2558. Take Gifts From the Richest Pile]] 🟢
4. [[1845. Seat Reservation Manager]] 🟡
5. [[3066. Minimum Operations to Exceed Threshold Value II]] 🟡

### Heapify
🔍 Nhận diện: cần dựng heap từ mảng có sẵn.
⏱ Mục tiêu: O(n) chứ không phải O(n log n). Hiểu vì sao sift-down từ n/2 về 0 là O(n).

1. [[973. K Closest Points to Origin]] 🟡 ⭐ (tự cài heapify)
2. [[215. Kth Largest Element in an Array]] 🟡
3. [[1985. Find the Kth Largest Integer in the Array]] 🟡

### Top-K & Merge-K
🔍 Nhận diện: "K phần tử lớn nhất/thường gặp nhất", "gộp K danh sách đã sắp xếp".
⏱ Mục tiêu: O(n log k) thay vì O(n log n).

1. [[347. Top K Frequent Elements]] 🟡 ⭐
2. [[692. Top K Frequent Words]] 🟡 ⭐ (comparator 2 tiêu chí)
3. [[23. Merge k Sorted Lists]] 🔴 ⭐
4. [[378. Kth Smallest Element in a Sorted Matrix]] 🟡 ⭐
5. [[373. Find K Pairs with Smallest Sums]] 🟡 ⭐
6. [[1439. Find the Kth Smallest Sum of a Matrix With Sorted Rows]] 🔴
7. [[719. Find K-th Smallest Pair Distance]] 🔴 (binary search on answer)

### Scheduling with Heap
🔍 Nhận diện: công việc có thời gian bắt đầu/độ ưu tiên, chọn việc tiếp theo tối ưu.

1. [[621. Task Scheduler]] 🟡 ⭐ (làm cả bản công thức toán và bản heap)
2. [[1834. Single-Threaded CPU]] 🟡 ⭐
3. [[502. IPO]] 🔴 ⭐ (2 heap, greedy)
4. [[1801. Number of Orders in the Backlog]] 🟡
5. [[355. Design Twitter]] 🟡 ⭐
6. [[253. Meeting Rooms II]] 🟡 🔒 → thay bằng [[1094. Car Pooling]] 🟡
7. [[767. Reorganize String]] 🟡 ⭐
8. [[1642. Furthest Building You Can Reach]] 🟡

### Two Heaps
🔍 Nhận diện: cần median hoặc cần chia dữ liệu thành "nửa nhỏ / nửa lớn".
⏱ Mục tiêu: insert O(log n), lấy median O(1). Bất biến: `maxHeap.size - minHeap.size ∈ {0, 1}`.

1. [[295. Find Median from Data Stream]] 🔴 ⭐
2. [[480. Sliding Window Median]] 🔴 (thêm lazy deletion)
3. [[1825. Finding MK Average]] 🔴
4. [[502. IPO]] 🔴

---

# **Backtracking**
> 📅 **Tuần 12–13** · Giai đoạn 3

> **Template chung**: `choose → explore → un-choose`. Luôn xác định rõ 3 thứ trước khi code: *trạng thái*, *điều kiện dừng*, *các lựa chọn tại mỗi bước*.

### Tree Maze (backtracking trên cây)
🔍 Nhận diện: liệt kê tất cả đường đi thỏa điều kiện trên cây.

1. [[112. Path Sum]] 🟢
2. [[113. Path Sum II]] 🟡 ⭐
3. [[257. Binary Tree Paths]] 🟢 ⭐
4. [[988. Smallest String Starting From Leaf]] 🟡

### Subsets
🔍 Nhận diện: "tất cả tập con", "power set", mỗi phần tử chọn hoặc không.
⏱ Mục tiêu: O(n · 2^n).

1. [[78. Subsets]] 🟢 ⭐ (làm cả 3 cách: đệ quy chọn/không, vòng lặp, bitmask)
2. [[90. Subsets II]] 🟡 ⭐ (sort trước rồi skip `nums[i] === nums[i-1]`)
3. [[1863. Sum of All Subset XOR Totals]] 🟢
4. [[2044. Count Number of Maximum Bitwise-OR Subsets]] 🟡

### Combinations
🔍 Nhận diện: "chọn k phần tử", "các bộ có tổng bằng target", thứ tự không quan trọng.
⏱ Mục tiêu: dùng tham số `start` để tránh sinh trùng.

1. [[77. Combinations]] 🟡 ⭐
2. [[39. Combination Sum]] 🟡 ⭐ (được dùng lại phần tử → truyền `i` chứ không `i+1`)
3. [[40. Combination Sum II]] 🟡 ⭐ (mỗi phần tử 1 lần + có trùng lặp)
4. [[216. Combination Sum III]] 🟡
5. [[377. Combination Sum IV]] 🟡 (thực chất là DP, không phải backtracking)
6. [[17. Letter Combinations of a Phone Number]] 🟡 ⭐
7. [[22. Generate Parentheses]] 🟡 ⭐ (ràng buộc `open < n`, `close < open`)

### Permutations
🔍 Nhận diện: "tất cả hoán vị", thứ tự **có** quan trọng.
⏱ Mục tiêu: O(n · n!).

1. [[46. Permutations]] 🟡 ⭐ (làm cả cách dùng `used[]` và cách swap tại chỗ)
2. [[47. Permutations II]] 🟡 ⭐
3. [[31. Next Permutation]] 🟡 ⭐ (không phải backtracking, nhưng cùng chủ đề)
4. [[60. Permutation Sequence]] 🔴
5. [[784. Letter Case Permutation]] 🟡

### Grid Backtracking
🔍 Nhận diện: tìm đường trong lưới có quay lui, cần đánh dấu rồi bỏ đánh dấu.

1. [[79. Word Search]] 🟡 ⭐
2. [[212. Word Search II]] 🔴 ⭐ (Trie + backtracking, không brute force từng từ)
3. [[980. Unique Paths III]] 🔴
4. [[489. Robot Room Cleaner]] 🔴 🔒

### Constraint Pruning
🔍 Nhận diện: nhiều ràng buộc cùng lúc, cần cắt nhánh sớm nếu không sẽ TLE.

1. [[51. N-Queens]] 🔴 ⭐ (dùng set cho cột, đường chéo `r+c`, `r-c`)
2. [[52. N-Queens II]] 🔴
3. [[37. Sudoku Solver]] 🔴 ⭐
4. [[473. Matchsticks to Square]] 🟡
5. [[1079. Letter Tile Possibilities]] 🟡

### Partition
🔍 Nhận diện: chia chuỗi/mảng thành các phần thỏa điều kiện.

1. [[131. Palindrome Partitioning]] 🟡 ⭐
2. [[93. Restore IP Addresses]] 🟡 ⭐
3. [[698. Partition to K Equal Sum Subsets]] 🟡 ⭐
4. [[139. Word Break]] 🟡 (bản backtracking + memo)
5. [[140. Word Break II]] 🔴

---

# **Tries**
> 📅 **Tuần 13** · Giai đoạn 3

🔍 Nhận diện: nhiều thao tác tra cứu theo **prefix**, autocomplete, tìm nhiều từ cùng lúc trong một văn bản, tìm cặp XOR lớn nhất.
⏱ Mục tiêu: insert/search O(L) với L là độ dài từ, không phụ thuộc số từ trong trie.

1. [[208. Implement Trie (Prefix Tree)]] 🟡 ⭐
2. [[211. Design Add and Search Words Data Structure]] 🟡 ⭐ (xử lý ký tự `.` bằng DFS)
3. [[212. Word Search II]] 🔴 ⭐
4. [[14. Longest Common Prefix]] 🟢
5. [[648. Replace Words]] 🟡 ⭐
6. [[677. Map Sum Pairs]] 🟡
7. [[1268. Search Suggestions System]] 🟡 ⭐
8. [[720. Longest Word in Dictionary]] 🟡
9. [[642. Design Search Autocomplete System]] 🔴 🔒
10. [[421. Maximum XOR of Two Numbers in an Array]] 🟡 ⭐ (**bit trie**, kỹ thuật riêng nên làm kỹ)
11. [[1707. Maximum XOR With an Element From Array]] 🔴
12. [[336. Palindrome Pairs]] 🔴

---

# **Graphs**
> 📅 **Tuần 14–15** · Giai đoạn 4

### Intro to Graphs
🔍 Nhận diện: dữ liệu là quan hệ giữa các đối tượng. Bước đầu tiên luôn là **dựng adjacency list**.

1. [[133. Clone Graph]] 🟡 ⭐ (HashMap old → new)
2. [[1971. Find if Path Exists in Graph]] 🟢 ⭐
3. [[997. Find the Town Judge]] 🟢 (đếm bậc vào/ra)
4. [[1436. Destination City]] 🟢

### Matrix DFS
🔍 Nhận diện: lưới 2D, đếm/đo vùng liên thông, lan tỏa từ một ô.
⏱ Mục tiêu: O(m·n). Nhớ mảng hướng `[[0,1],[1,0],[0,-1],[-1,0]]`.

1. [[733. Flood Fill]] 🟢 ⭐
2. [[200. Number of Islands]] 🟡 ⭐
3. [[695. Max Area of Island]] 🟡 ⭐
4. [[463. Island Perimeter]] 🟢
5. [[130. Surrounded Regions]] 🟡 ⭐ (DFS từ biên vào, kỹ thuật đảo ngược)
6. [[1020. Number of Enclaves]] 🟡
7. [[417. Pacific Atlantic Water Flow]] 🟡 ⭐ (2 lượt DFS từ 2 biên)
8. [[79. Word Search]] 🟡
9. [[1254. Number of Closed Islands]] 🟡
10. [[827. Making A Large Island]] 🔴 ⭐ (đánh id cho từng đảo)
11. [[329. Longest Increasing Path in a Matrix]] 🔴 ⭐ (DFS + memo)

### Matrix BFS
🔍 Nhận diện: "số bước ít nhất", lan tỏa đồng thời từ nhiều nguồn, cạnh không trọng số.
⏱ Mục tiêu: O(m·n).

1. [[994. Rotting Oranges]] 🟡 ⭐ (multi-source BFS)
2. [[542. 01 Matrix]] 🟡 ⭐ (multi-source BFS)
3. [[286. Walls and Gates]] 🟡 🔒 → thay bằng [[542. 01 Matrix]]
4. [[1091. Shortest Path in Binary Matrix]] 🟡 ⭐ (8 hướng)
5. [[909. Snakes and Ladders]] 🟡
6. [[1730. Shortest Path to Get Food]] 🟡 🔒
7. [[1293. Shortest Path in a Grid with Obstacles Elimination]] 🔴 ⭐ (BFS với state `(r, c, k)`)
8. [[752. Open the Lock]] 🟡 ⭐ (BFS trên không gian trạng thái)
9. [[773. Sliding Puzzle]] 🔴
10. [[1926. Nearest Exit from Entrance in Maze]] 🟡

### Adjacency List
🔍 Nhận diện: đồ thị tổng quát không phải lưới.

1. [[323. Number of Connected Components in an Undirected Graph]] 🟡 🔒 → thay bằng [[547. Number of Provinces]] 🟡 ⭐
2. [[261. Graph Valid Tree]] 🟡 🔒 → thay bằng [[684. Redundant Connection]] 🟡
3. [[127. Word Ladder]] 🔴 ⭐ (BFS + dựng đồ thị ngầm)
4. [[126. Word Ladder II]] 🔴
5. [[399. Evaluate Division]] 🟡 ⭐ (đồ thị có trọng số nhân)
6. [[1466. Reorder Routes to Make All Paths Lead to the City Zero]] 🟡
7. [[841. Keys and Rooms]] 🟡
8. [[2192. All Ancestors of a Node in a Directed Acyclic Graph]] 🟡

### Cycle Detection
🔍 Nhận diện: "có thể hoàn thành tất cả không", "có chu trình không", "là cây hay không".
⏱ Mục tiêu: có hướng dùng 3 màu (trắng/xám/đen), vô hướng dùng parent hoặc Union-Find.

1. [[207. Course Schedule]] 🟡 ⭐
2. [[802. Find Eventual Safe States]] 🟡 ⭐
3. [[684. Redundant Connection]] 🟡 ⭐
4. [[685. Redundant Connection II]] 🔴
5. [[1059. All Paths from Source Lead to Destination]] 🟡 🔒

### Bipartite / Graph Coloring
🔍 Nhận diện: "chia làm 2 nhóm", "hai người không thích nhau không cùng nhóm".
⏱ Mục tiêu: BFS/DFS tô 2 màu, O(V + E).

1. [[785. Is Graph Bipartite?]] 🟡 ⭐
2. [[886. Possible Bipartition]] 🟡 ⭐
3. [[1042. Flower Planting With No Adjacent]] 🟡

### Union-Find (DSU) ⭐⭐
🔍 Nhận diện: liên tục gộp nhóm và hỏi "hai phần tử có cùng nhóm không", đếm số nhóm, phát hiện chu trình trong đồ thị vô hướng, xử lý truy vấn offline.
⏱ Mục tiêu: gần O(1) mỗi thao tác với path compression + union by rank/size.

1. [[547. Number of Provinces]] 🟡 ⭐
2. [[684. Redundant Connection]] 🟡 ⭐
3. [[990. Satisfiability of Equality Equations]] 🟡 ⭐
4. [[721. Accounts Merge]] 🟡 ⭐
5. [[1202. Smallest String With Swaps]] 🟡
6. [[839. Similar String Groups]] 🔴
7. [[128. Longest Consecutive Sequence]] 🟡 (bản Union-Find)
8. [[959. Regions Cut By Slashes]] 🟡
9. [[305. Number of Islands II]] 🔴 🔒
10. [[1697. Checking Existence of Edge Length Limited Paths]] 🔴 ⭐ (offline queries)
11. [[2421. Number of Good Paths]] 🔴
12. [[947. Most Stones Removed with Same Row or Column]] 🟡

---

# **Advanced Graphs**
> 📅 **Tuần 16** · Giai đoạn 4

### Dijkstra's
🔍 Nhận diện: đường đi ngắn nhất, **trọng số dương**. Nếu bài có thêm ràng buộc phụ (số lần dùng discount, số chướng ngại được phá) thì mở rộng state thành `dist[node][k]`.
⏱ Mục tiêu: O(E log V) với min-heap.

1. [[743. Network Delay Time]] 🟡 ⭐
2. [[1631. Path With Minimum Effort]] 🟡 ⭐ (Dijkstra biến thể minimax)
3. [[778. Swim in Rising Water]] 🔴 ⭐
4. [[1514. Path with Maximum Probability]] 🟡
5. [[2093. Minimum Cost to Reach City With Discounts]] 🟡 ⭐ (state 2 chiều)
6. [[787. Cheapest Flights Within K Stops]] 🟡
7. [[1976. Number of Ways to Arrive at Destination]] 🟡 ⭐ (Dijkstra + đếm đường)
8. [[2290. Minimum Obstacle Removal to Reach Corner]] 🔴 (0-1 BFS)
9. [[1368. Minimum Cost to Make at Least One Valid Path in a Grid]] 🔴 ⭐ (**0-1 BFS** với deque)

### Bellman-Ford / SPFA
🔍 Nhận diện: có **trọng số âm**, hoặc giới hạn "nhiều nhất k cạnh", hoặc cần phát hiện chu trình âm.
⏱ Mục tiêu: O(V·E).

1. [[787. Cheapest Flights Within K Stops]] 🟡 ⭐ (phải copy mảng dist mỗi vòng)
2. [[1928. Minimum Cost to Reach Destination in Time]] 🔴
3. [[2093. Minimum Cost to Reach City With Discounts]] 🟡

### Floyd-Warshall
🔍 Nhận diện: cần khoảng cách giữa **mọi cặp** đỉnh, V nhỏ (≤ 400).
⏱ Mục tiêu: O(V³), code chỉ 3 vòng for lồng nhau (nhớ k ở vòng ngoài cùng).

1. [[1334. Find the City With the Smallest Number of Neighbors at a Threshold Distance]] 🟡 ⭐
2. [[1462. Course Schedule IV]] 🟡 ⭐
3. [[2976. Minimum Cost to Convert String I]] 🟡

### Prim's
🔍 Nhận diện: nối tất cả đỉnh với tổng trọng số nhỏ nhất, đồ thị **dày**.
⏱ Mục tiêu: O(E log V).

1. [[1584. Min Cost to Connect All Points]] 🟡 ⭐
2. [[1135. Connecting Cities With Minimum Cost]] 🟡 🔒 → thay bằng [[1584]]

### Kruskal's
🔍 Nhận diện: giống Prim nhưng đồ thị **thưa**, hoặc bài yêu cầu xử lý cạnh theo thứ tự trọng số tăng dần.
⏱ Mục tiêu: O(E log E), cần Union-Find.

1. [[1584. Min Cost to Connect All Points]] 🟡 ⭐ (bản DSU)
2. [[1697. Checking Existence of Edge Length Limited Paths]] 🔴 ⭐
3. [[1489. Find Critical and Pseudo-Critical Edges in Minimum Spanning Tree]] 🔴
4. [[778. Swim in Rising Water]] 🔴 (bản Union-Find)

### Topological Sort
🔍 Nhận diện: "thứ tự thực hiện", "điều kiện tiên quyết", DAG.
⏱ Mục tiêu: O(V + E). Làm cả 2 cách: Kahn (BFS, đếm indegree) và DFS post-order đảo ngược.

1. [[207. Course Schedule]] 🟡 ⭐
2. [[210. Course Schedule II]] 🟡 ⭐
3. [[269. Alien Dictionary]] 🔴 🔒 ⭐ → thay bằng [[953. Verifying an Alien Dictionary]] 🟢 + [[210]]
4. [[310. Minimum Height Trees]] 🟡 ⭐ (bóc lá từng lớp)
5. [[2115. Find All Possible Recipes from Given Supplies]] 🟡
6. [[1462. Course Schedule IV]] 🟡
7. [[1136. Parallel Courses]] 🟡 🔒
8. [[2392. Build a Matrix With Conditions]] 🔴

### SCC / Bridges / Eulerian Path  ·  ⏭ Tuần 21
🔍 Nhận diện: "cạnh critical", "thành phần liên thông mạnh", "đi qua mỗi cạnh đúng 1 lần".
> Nhóm này hiếm gặp trong phỏng vấn product company. Chỉ làm nếu nhắm FAANG hoặc competitive.

1. [[1192. Critical Connections in a Network]] 🔴 ⭐ (Tarjan tìm bridge)
2. [[332. Reconstruct Itinerary]] 🔴 ⭐ (Hierholzer, Eulerian path)
3. [[753. Cracking the Safe]] 🔴 (Eulerian circuit trên đồ thị De Bruijn)
4. [[2101. Detonate the Maximum Bombs]] 🟡

---

# **1-D Dynamic Programming**
> 📅 **Tuần 17–18** · Giai đoạn 5

> **Quy trình bắt buộc cho mọi bài DP**:
> 1. Định nghĩa `dp[i]` bằng **một câu tiếng Việt rõ ràng**. Nếu không viết được câu này thì chưa hiểu bài.
> 2. Viết công thức truy hồi.
> 3. Xác định base case.
> 4. Xác định thứ tự duyệt.
> 5. Tối ưu bộ nhớ nếu chỉ phụ thuộc vài trạng thái trước.

### 1-Dimension DP
🔍 Nhận diện: "có bao nhiêu cách", "ít nhất/nhiều nhất bao nhiêu", quyết định tại vị trí i chỉ phụ thuộc vài vị trí trước.
⏱ Mục tiêu: O(n) hoặc O(n·k).

1. [[70. Climbing Stairs]] 🟢 ⭐
2. [[746. Min Cost Climbing Stairs]] 🟢 ⭐
3. [[198. House Robber]] 🟡 ⭐
4. [[213. House Robber II]] 🟡 ⭐ (chạy 2 lần trên 2 đoạn)
5. [[740. Delete and Earn]] 🟡 (biến đổi về House Robber)
6. [[91. Decode Ways]] 🟡 ⭐ (nhiều edge case với số 0)
7. [[139. Word Break]] 🟡 ⭐
8. [[322. Coin Change]] 🟡 ⭐ (bài mẫu quan trọng nhất)
9. [[279. Perfect Squares]] 🟡
10. [[152. Maximum Product Subarray]] 🟡 ⭐ (giữ cả max và min)
11. [[983. Minimum Cost For Tickets]] 🟡
12. [[64. Minimum Path Sum]] 🟡
13. [[1137. N-th Tribonacci Number]] 🟢
14. [[2466. Count Ways To Build Good Strings]] 🟡
15. [[1043. Partition Array for Maximum Sum]] 🟡
16. [[2140. Solving Questions With Brainpower]] 🟡

### Palindromes
🔍 Nhận diện: "palindrome dài nhất", "đếm số palindrome con".
⏱ Mục tiêu: expand-around-center O(n²) time O(1) space, hoặc DP O(n²) cả hai.

1. [[5. Longest Palindromic Substring]] 🟡 ⭐ (expand around center)
2. [[647. Palindromic Substrings]] 🟡 ⭐
3. [[516. Longest Palindromic Subsequence]] 🟡 ⭐ (khác substring, đây là DP 2D)
4. [[131. Palindrome Partitioning]] 🟡
5. [[132. Palindrome Partitioning II]] 🔴
6. [[1312. Minimum Insertion Steps to Make a String Palindrome]] 🔴 ⭐ (= n - LPS)
7. [[9. Palindrome Number]] 🟢
8. [[214. Shortest Palindrome]] 🔴 (KMP)

### Longest Increasing Subsequence
🔍 Nhận diện: "dãy con tăng dài nhất", hoặc bài có thể quy về LIS sau khi sort theo 1 chiều.
⏱ Mục tiêu: O(n²) bản cơ bản, O(n log n) bản patience sorting.

1. [[300. Longest Increasing Subsequence]] 🟡 ⭐ (cài cả 2 bản)
2. [[673. Number of Longest Increasing Subsequence]] 🟡
3. [[354. Russian Doll Envelopes]] 🔴 ⭐ (sort width tăng, height giảm rồi LIS)
4. [[1626. Best Team With No Conflicts]] 🟡
5. [[646. Maximum Length of Pair Chain]] 🟡
6. [[1964. Find the Longest Valid Obstacle Course at Each Position]] 🔴
7. [[368. Largest Divisible Subset]] 🟡 ⭐ (LIS + truy vết)

### State Machine DP (chuỗi bài Stock)
🔍 Nhận diện: tại mỗi thời điểm có vài trạng thái rời rạc (đang giữ / không giữ / cooldown), chuyển đổi giữa các trạng thái.
⏱ Mục tiêu: O(n·k) với k là số trạng thái.

1. [[121. Best Time to Buy and Sell Stock]] 🟢 ⭐
2. [[122. Best Time to Buy and Sell Stock II]] 🟡 ⭐
3. [[309. Best Time to Buy and Sell Stock with Cooldown]] 🟡 ⭐
4. [[714. Best Time to Buy and Sell Stock with Transaction Fee]] 🟡 ⭐
5. [[123. Best Time to Buy and Sell Stock III]] 🔴
6. [[188. Best Time to Buy and Sell Stock IV]] 🔴 ⭐ (tổng quát hóa cả chuỗi)

### Jump / Reachability DP
1. [[55. Jump Game]] 🟡 ⭐ (làm cả DP và Greedy, so sánh)
2. [[45. Jump Game II]] 🟡 ⭐
3. [[1306. Jump Game III]] 🟡 (thực chất là BFS/DFS)
4. [[1871. Jump Game VII]] 🟡
5. [[1696. Jump Game VI]] 🟡 (DP + monotonic deque)

---

# **2-D Dynamic Programming**
> 📅 **Tuần 19** · Giai đoạn 5

### 2-Dimension DP
🔍 Nhận diện: trạng thái cần 2 chỉ số, thường là 2 chuỗi hoặc lưới 2D.
⏱ Mục tiêu: O(m·n). Luôn cân nhắc tối ưu về O(min(m,n)) bộ nhớ bằng rolling array.

1. [[62. Unique Paths]] 🟡 ⭐
2. [[63. Unique Paths II]] 🟡
3. [[64. Minimum Path Sum]] 🟡 ⭐
4. [[120. Triangle]] 🟡 ⭐ (duyệt từ dưới lên)
5. [[931. Minimum Falling Path Sum]] 🟡
6. [[221. Maximal Square]] 🟡 ⭐
7. [[1277. Count Square Submatrices with All Ones]] 🟡
8. [[174. Dungeon Game]] 🔴 ⭐ (duyệt ngược từ đích về nguồn)
9. [[329. Longest Increasing Path in a Matrix]] 🔴
10. [[1301. Number of Paths with Max Score]] 🔴
11. [[576. Out of Boundary Paths]] 🟡

### 0/1 Knapsack
🔍 Nhận diện: mỗi món **chọn tối đa 1 lần**, có sức chứa/ngân sách giới hạn, hỏi tối ưu hoặc đếm cách.
⏱ Mục tiêu: O(n·W). Bản 1D **phải duyệt capacity giảm dần**.

1. [[416. Partition Equal Subset Sum]] 🟡 ⭐
2. [[494. Target Sum]] 🟡 ⭐ (biến đổi về subset sum)
3. [[474. Ones and Zeroes]] 🟡 ⭐ (knapsack 2 chiều)
4. [[1049. Last Stone Weight II]] 🟡 ⭐
5. [[698. Partition to K Equal Sum Subsets]] 🟡
6. [[2915. Length of the Longest Subsequence That Sums to Target]] 🟡

### Unbounded Knapsack
🔍 Nhận diện: mỗi món **dùng không giới hạn số lần**.
⏱ Mục tiêu: O(n·W). Bản 1D duyệt capacity **tăng dần**.

1. [[322. Coin Change]] 🟡 ⭐
2. [[518. Coin Change II]] 🟡 ⭐ (đếm **tổ hợp**: vòng ngoài là coin)
3. [[377. Combination Sum IV]] 🟡 ⭐ (đếm **hoán vị**: vòng ngoài là target — so sánh kỹ với 518)
4. [[279. Perfect Squares]] 🟡
5. [[139. Word Break]] 🟡
6. [[343. Integer Break]] 🟡
7. [[983. Minimum Cost For Tickets]] 🟡

### LCS (dãy con chung / chỉnh sửa chuỗi)
🔍 Nhận diện: hai chuỗi, hỏi độ dài chung, số phép biến đổi, đếm cách khớp.
⏱ Mục tiêu: O(m·n).

1. [[1143. Longest Common Subsequence]] 🟡 ⭐
2. [[72. Edit Distance]] 🟡 ⭐
3. [[583. Delete Operation for Two Strings]] 🟡
4. [[712. Minimum ASCII Delete Sum for Two Strings]] 🟡
5. [[97. Interleaving String]] 🟡 ⭐
6. [[115. Distinct Subsequences]] 🔴 ⭐
7. [[718. Maximum Length of Repeated Subarray]] 🟡 (LCS cho subarray)
8. [[1035. Uncrossed Lines]] 🟡 (LCS trá hình)

### String Matching DP
🔍 Nhận diện: pattern có ký tự đặc biệt `*`, `.`, `?`.

1. [[10. Regular Expression Matching]] 🔴 ⭐
2. [[44. Wildcard Matching]] 🔴 ⭐
3. [[2060. Check if an Original String Exists Given Two Encoded Strings]] 🔴

### Interval DP  ·  ⏭ Tuần 21
🔍 Nhận diện: "xóa/đốt/cắt phần tử ở giữa", kết quả phụ thuộc thứ tự xử lý, `dp[i][j]` = kết quả tối ưu trên đoạn [i, j].
⏱ Mục tiêu: O(n³). Duyệt theo **độ dài đoạn tăng dần**.

1. [[312. Burst Balloons]] 🔴 ⭐ (nghĩ ngược: chọn quả nổ **cuối cùng**)
2. [[1547. Minimum Cost to Cut a Stick]] 🔴 ⭐
3. [[375. Guess Number Higher or Lower II]] 🟡
4. [[1039. Minimum Score Triangulation of Polygon]] 🟡
5. [[546. Remove Boxes]] 🔴
6. [[516. Longest Palindromic Subsequence]] 🟡

### Bitmask DP  ·  ⏭ Tuần 21
🔍 Nhận diện: **n ≤ 20**, cần theo dõi "tập nào đã dùng".
⏱ Mục tiêu: O(2^n · n).

1. [[698. Partition to K Equal Sum Subsets]] 🟡 ⭐
2. [[847. Shortest Path Visiting All Nodes]] 🔴 ⭐ (BFS + bitmask)
3. [[1125. Smallest Sufficient Team]] 🔴
4. [[1349. Maximum Students Taking Exam]] 🔴
5. [[526. Beautiful Arrangement]] 🟡 ⭐
6. [[1595. Minimum Cost to Connect Two Groups of Points]] 🔴
7. [[943. Find the Shortest Superstring]] 🔴 (TSP)

### Digit DP  ·  ⏭ Tuần 21
🔍 Nhận diện: "đếm số nguyên trong [L, R] thỏa tính chất về chữ số". Hiếm gặp nhưng xuất hiện ở Google.

1. [[902. Numbers At Most N Given Digit Set]] 🔴
2. [[233. Number of Digit One]] 🔴
3. [[600. Non-negative Integers without Consecutive Ones]] 🔴

---

# **Greedy**
> 📅 **Tuần 20** · Giai đoạn 6

> **Cách kiểm tra greedy có đúng không**: chứng minh bằng *exchange argument* (nếu có lời giải tối ưu khác lựa chọn greedy, ta có thể hoán đổi mà không làm tệ đi). Nếu không chứng minh được, khả năng cao phải dùng DP.

### Kadane's Algorithm
🔍 Nhận diện: "subarray liên tiếp có tổng lớn nhất", có số âm.
⏱ Mục tiêu: O(n) time, O(1) space.

1. [[53. Maximum Subarray]] 🟢 ⭐
2. [[918. Maximum Sum Circular Subarray]] 🟡 ⭐ (total - minSubarray, bẫy khi tất cả đều âm)
3. [[152. Maximum Product Subarray]] 🟡 ⭐
4. [[1567. Maximum Length of Subarray With Positive Product]] 🟡
5. [[978. Longest Turbulent Subarray]] 🟡

### Greedy trên mảng / Exchange Argument
🔍 Nhận diện: chọn cục bộ tối ưu tại mỗi bước và chứng minh được là tối ưu toàn cục.

1. [[55. Jump Game]] 🟡 ⭐
2. [[45. Jump Game II]] 🟡 ⭐
3. [[134. Gas Station]] 🟡 ⭐
4. [[763. Partition Labels]] 🟡 ⭐
5. [[678. Valid Parenthesis String]] 🟡 ⭐ (giữ khoảng `[lo, hi]`)
6. [[846. Hand of Straights]] 🟡 ⭐
7. [[1899. Merge Triplets to Form Target Triplet]] 🟡
8. [[455. Assign Cookies]] 🟢
9. [[1029. Two City Scheduling]] 🟡 ⭐
10. [[406. Queue Reconstruction by Height]] 🟡 ⭐
11. [[621. Task Scheduler]] 🟡
12. [[2405. Optimal Partition of String]] 🟡
13. [[135. Candy]] 🔴 ⭐ (2 lượt duyệt)
14. [[871. Minimum Number of Refueling Stops]] 🔴 (greedy + heap)
15. [[1005. Maximize Sum Of Array After K Negations]] 🟢

---

# **Intervals**
> 📅 **Tuần 20** · Giai đoạn 6

🔍 Nhận diện: dữ liệu dạng `[start, end]`. **Bước đầu tiên luôn là sort** — theo `start` nếu cần gộp, theo `end` nếu cần chọn nhiều nhất không chồng lấn.

### Merge / Insert
⏱ Mục tiêu: O(n log n) do sort.

1. [[57. Insert Interval]] 🟡 ⭐ (không cần sort, O(n))
2. [[56. Merge Intervals]] 🟡 ⭐
3. [[986. Interval List Intersections]] 🟡 ⭐
4. [[759. Employee Free Time]] 🔴 🔒 → thay bằng [[56]] + [[986]]
5. [[228. Summary Ranges]] 🟢

### Non-overlapping (interval scheduling)
🔍 Nhận diện: "xóa ít nhất bao nhiêu khoảng", "chọn nhiều nhất bao nhiêu khoảng không chồng lấn". **Sort theo `end`**.

1. [[435. Non-overlapping Intervals]] 🟡 ⭐
2. [[452. Minimum Number of Arrows to Burst Balloons]] 🟡 ⭐
3. [[646. Maximum Length of Pair Chain]] 🟡

### Meeting Rooms / Sweep Line
🔍 Nhận diện: "cần bao nhiêu phòng", "số sự kiện đồng thời lớn nhất". Tách mỗi khoảng thành 2 sự kiện `(start, +1)` và `(end, -1)` rồi sort.

1. [[252. Meeting Rooms]] 🟢 🔒 → thay bằng [[435]]
2. [[253. Meeting Rooms II]] 🟡 🔒 ⭐ → thay bằng [[1094. Car Pooling]] 🟡 (cùng pattern, free)
3. [[1094. Car Pooling]] 🟡 ⭐ (difference array)
4. [[1109. Corporate Flight Bookings]] 🟡
5. [[218. The Skyline Problem]] 🔴 ⭐ (sweep line + heap, bài kinh điển)
6. [[732. My Calendar III]] 🔴
7. [[729. My Calendar I]] 🟡 ⭐
8. [[731. My Calendar II]] 🟡
9. [[2251. Number of Flowers in Full Bloom]] 🔴 ⭐ (sweep line + binary search)

### Interval + DP / Heap
1. [[1851. Minimum Interval to Include Each Query]] 🔴 ⭐
2. [[1235. Maximum Profit in Job Scheduling]] 🔴 ⭐ (sort + DP + binary search)
3. [[2008. Maximum Earnings From Taxi]] 🟡

---

# **Math & Geometry**
> 📅 **Tuần 20** · Giai đoạn 6

### Matrix Simulation
🔍 Nhận diện: xoay, duyệt xoắn ốc, biến đổi tại chỗ trên ma trận.
⏱ Mục tiêu: thường yêu cầu O(1) extra space.

1. [[48. Rotate Image]] 🟡 ⭐ (transpose rồi đảo từng hàng)
2. [[54. Spiral Matrix]] 🟡 ⭐ (4 biên co dần)
3. [[59. Spiral Matrix II]] 🟡
4. [[73. Set Matrix Zeroes]] 🟡 ⭐ (dùng hàng 0 và cột 0 làm cờ đánh dấu)
5. [[289. Game of Life]] 🟡 ⭐ (mã hóa 2 trạng thái vào 1 số)
6. [[867. Transpose Matrix]] 🟢
7. [[1424. Diagonal Traverse II]] 🟡

### Number Theory
🔍 Nhận diện: số nguyên tố, ước chung, lũy thừa lớn, modulo.

1. [[204. Count Primes]] 🟡 ⭐ (Sieve of Eratosthenes, O(n log log n))
2. [[1071. Greatest Common Divisor of Strings]] 🟢 ⭐ (Euclid)
3. [[1979. Find Greatest Common Divisor of Array]] 🟢
4. [[50. Pow(x, n)]] 🟡 ⭐
5. [[372. Super Pow]] 🟡
6. [[1922. Count Good Numbers]] 🟡 (fast pow + modulo)
7. [[172. Factorial Trailing Zeroes]] 🟡
8. [[326. Power of Three]] 🟢
9. [[62. Unique Paths]] 🟡 (bản tổ hợp C(m+n-2, m-1))

### Big Number / String Simulation
1. [[66. Plus One]] 🟢
2. [[43. Multiply Strings]] 🟡 ⭐
3. [[415. Add Strings]] 🟢 ⭐
4. [[989. Add to Array-Form of Integer]] 🟢
5. [[7. Reverse Integer]] 🟡 (xử lý tràn số 32-bit)
6. [[8. String to Integer (atoi)]] 🟡
7. [[29. Divide Two Integers]] 🟡 ⭐ (chia bằng dịch bit)
8. [[202. Happy Number]] 🟢

### Randomization
🔍 Nhận diện: "random uniform", "shuffle", "pick với xác suất tỉ lệ".

1. [[384. Shuffle an Array]] 🟡 ⭐ (Fisher-Yates, chứng minh được tính đều)
2. [[528. Random Pick with Weight]] 🟡 ⭐
3. [[382. Linked List Random Node]] 🟡 ⭐ (reservoir sampling)
4. [[398. Random Pick Index]] 🟡
5. [[380. Insert Delete GetRandom O(1)]] 🟡 ⭐
6. [[381. Insert Delete GetRandom O(1) - Duplicates allowed]] 🔴
7. [[470. Implement Rand10() Using Rand7()]] 🟡 ⭐ (rejection sampling)

### Geometry
1. [[2013. Detect Squares]] 🟡 ⭐
2. [[149. Max Points on a Line]] 🔴 ⭐ (dùng slope dạng phân số tối giản, tránh số thực)
3. [[836. Rectangle Overlap]] 🟢
4. [[223. Rectangle Area]] 🟡
5. [[587. Erect the Fence]] 🔴 (convex hull, Andrew's monotone chain)
6. [[593. Valid Square]] 🟡

---

# **Bit Manipulation**
> 📅 **Tuần 20** · Giai đoạn 6

### Bit Operations
🔍 Nhận diện: đề nhắc tới bit, hoặc yêu cầu O(1) space với tập hợp nhỏ, hoặc cấm dùng `+`/`-`.
⏱ Mục tiêu: nhớ các mẹo: `n & (n-1)` xóa bit 1 cuối cùng · `n & -n` lấy bit 1 cuối cùng · `n & (n-1) === 0` kiểm tra lũy thừa 2.

1. [[191. Number of 1 Bits]] 🟢 ⭐
2. [[338. Counting Bits]] 🟢 ⭐ (DP trên bit)
3. [[190. Reverse Bits]] 🟢 ⭐
4. [[231. Power of Two]] 🟢
5. [[371. Sum of Two Integers]] 🟡 ⭐ (cộng không dùng `+`)
6. [[201. Bitwise AND of Numbers Range]] 🟡 ⭐ (tìm common prefix)
7. [[461. Hamming Distance]] 🟢
8. [[476. Number Complement]] 🟢
9. [[1009. Complement of Base 10 Integer]] 🟢

### XOR Tricks
🔍 Nhận diện: "xuất hiện một lần trong khi các số khác xuất hiện hai lần", "tìm số thiếu", các cặp triệt tiêu nhau.
⏱ Mục tiêu: O(n) time, O(1) space. Nhớ: `a ^ a = 0`, `a ^ 0 = a`, XOR có tính giao hoán.

1. [[136. Single Number]] 🟢 ⭐
2. [[268. Missing Number]] 🟢 ⭐
3. [[137. Single Number II]] 🟡 ⭐ (đếm bit mod 3)
4. [[260. Single Number III]] 🟡 ⭐ (tách 2 nhóm bằng bit khác nhau)
5. [[1310. XOR Queries of a Subarray]] 🟡
6. [[421. Maximum XOR of Two Numbers in an Array]] 🟡 ⭐
7. [[1863. Sum of All Subset XOR Totals]] 🟢
8. [[2433. Find The Original Array of Prefix Xor]] 🟡

### Bitmask Enumeration
🔍 Nhận diện: n ≤ 20, cần duyệt mọi tập con.
⏱ Mục tiêu: O(2^n). Mẹo duyệt mọi tập con của mask: `for (let s = mask; s > 0; s = (s-1) & mask)`.

1. [[78. Subsets]] 🟢 ⭐ (bản bitmask)
2. [[2044. Count Number of Maximum Bitwise-OR Subsets]] 🟡
3. [[1178. Number of Valid Words for Each Puzzle]] 🔴
4. [[1239. Maximum Length of a Concatenated String with Unique Characters]] 🟡 ⭐
5. [[2151. Maximum Good People Based on Statements]] 🔴

---

# **Segment Tree & Fenwick Tree**
> 📅 **Tuần 21** · Giai đoạn 7 · nâng cao, có thể bỏ

🔍 Nhận diện: **range query + point/range update** đan xen nhau. Nếu chỉ query mà không update → dùng prefix sum, rẻ hơn nhiều.
⏱ Mục tiêu: build O(n), query và update O(log n).

### Fenwick Tree (Binary Indexed Tree)
> Ngắn hơn segment tree, nhưng chỉ làm được prefix-based (sum, count). Ưu tiên học cái này trước.

1. [[307. Range Sum Query - Mutable]] 🟡 ⭐
2. [[315. Count of Smaller Numbers After Self]] 🔴 ⭐ (BIT trên giá trị nén tọa độ)
3. [[493. Reverse Pairs]] 🔴 ⭐
4. [[327. Count of Range Sum]] 🔴
5. [[1395. Count Number of Teams]] 🟡

### Segment Tree
> Mạnh hơn: làm được min/max/gcd trên đoạn, và lazy propagation cho range update.

1. [[307. Range Sum Query - Mutable]] 🟡 (bản segment tree, so sánh với BIT)
2. [[699. Falling Squares]] 🔴 ⭐
3. [[732. My Calendar III]] 🔴 ⭐ (lazy propagation)
4. [[715. Range Module]] 🔴
5. [[218. The Skyline Problem]] 🔴
6. [[2407. Longest Increasing Subsequence II]] 🔴 ⭐ (LIS với segment tree max)

---

# **String Algorithms**
> 📅 **Tuần 21** · Giai đoạn 7 · nâng cao, có thể bỏ

### KMP
🔍 Nhận diện: tìm pattern trong text, "prefix cũng là suffix", chuỗi lặp.
⏱ Mục tiêu: O(n + m). Cốt lõi là mảng LPS (longest proper prefix which is also suffix).

1. [[28. Find the Index of the First Occurrence in a String]] 🟢 ⭐
2. [[459. Repeated Substring Pattern]] 🟢 ⭐
3. [[1392. Longest Happy Prefix]] 🔴 ⭐
4. [[214. Shortest Palindrome]] 🔴
5. [[3008. Find Beautiful Indices in the Given Array II]] 🔴

### Rolling Hash (Rabin-Karp)
🔍 Nhận diện: so sánh nhiều substring, "chuỗi con lặp dài nhất", cần hash cửa sổ trượt.
⏱ Mục tiêu: O(n) trung bình. Nhớ chọn base và mod là số nguyên tố lớn.

1. [[187. Repeated DNA Sequences]] 🟡 ⭐
2. [[1044. Longest Duplicate Substring]] 🔴 ⭐ (binary search + rolling hash)
3. [[1698. Number of Distinct Substrings in a String]] 🟡 🔒
4. [[2168. Unique Substrings With Equal Digit Frequency]] 🟡 🔒

### Manacher  ·  ⏭ Tuần 21
1. [[5. Longest Palindromic Substring]] 🟡 (bản O(n), chỉ học nếu có thời gian)

---
---

# 🎯 CORE 150 — Danh sách tối thiểu đi phỏng vấn

Nếu chỉ còn 6 tuần, làm đúng các bài `⭐` trong các nhóm sau, theo thứ tự:

| Thứ tự | Nhóm | Số bài ⭐ |
|---|---|---|
| 1 | Arrays & Hashing + Prefix Sum | 12 |
| 2 | Two Pointers | 10 |
| 3 | Sliding Window | 9 |
| 4 | Stack + Monotonic Stack | 12 |
| 5 | Binary Search + on Answer | 14 |
| 6 | Linked List | 14 |
| 7 | Trees (DFS/BFS/BST) | 22 |
| 8 | Heap | 12 |
| 9 | Backtracking | 14 |
| 10 | Trie | 5 |
| 11 | Graphs + Union-Find | 20 |
| 12 | DP 1D + 2D | 25 |
| 13 | Greedy + Intervals | 14 |
| 14 | Bit + Math | 12 |

Tổng khoảng **195 bài ⭐**. Làm hết số này là đủ phủ pattern cho hầu hết công ty.

---

# 🔒 Phụ lục: Bài Premium và thay thế miễn phí

| Premium | Thay thế miễn phí | Cùng pattern |
|---|---|---|
| 271. Encode and Decode Strings | 443. String Compression | Serialize chuỗi |
| 259. 3Sum Smaller | 611. Valid Triangle Number | Two pointers đếm |
| 340. Longest Substring with At Most K Distinct | 2024. Maximize the Confusion of an Exam | Sliding window variable |
| 323. Number of Connected Components | 547. Number of Provinces | Union-Find / DFS |
| 261. Graph Valid Tree | 684. Redundant Connection | Cycle detection |
| 286. Walls and Gates | 542. 01 Matrix | Multi-source BFS |
| 252/253. Meeting Rooms I & II | 1094. Car Pooling | Sweep line |
| 269. Alien Dictionary | 210. Course Schedule II | Topological sort |
| 370. Range Addition | 2381. Shifting Letters II | Difference array |
| 285. Inorder Successor in BST | 173. BST Iterator | Inorder iterative |
| 1650. LCA III | 160. Intersection of Two Linked Lists | Two pointers hội tụ |
| 346. Moving Average from Data Stream | 643. Maximum Average Subarray I | Fixed window |

---

# 📊 Phụ lục: Cheat sheet độ phức tạp

| Cấu trúc | Truy cập | Tìm kiếm | Chèn | Xóa |
|---|---|---|---|---|
| Array | O(1) | O(n) | O(n) | O(n) |
| Dynamic Array (push) | O(1) | O(n) | O(1)* | O(n) |
| Linked List | O(n) | O(n) | O(1) | O(1) |
| Hash Table | — | O(1)* | O(1)* | O(1)* |
| BST (cân bằng) | O(log n) | O(log n) | O(log n) | O(log n) |
| Heap | O(1) peek | O(n) | O(log n) | O(log n) |
| Trie | — | O(L) | O(L) | O(L) |
| Union-Find | — | ~O(1) | — | — |
| Fenwick / Segment Tree | — | O(log n) | O(log n) | O(log n) |

\* trung bình / amortized

---

# JavaScript
> 📅 **Tuần 1–2** · viết sẵn template rồi dùng cả lộ trình

### Cú pháp và thư viện cần thuộc
- `Map` / `Set`: `.get`, `.set`, `.has`, `.delete`, `.size`. Duyệt theo đúng thứ tự chèn (quan trọng khi làm LRU).
- Sort số: `arr.sort((a, b) => a - b)`. Mặc định sort theo **string**, đây là lỗi hay gặp nhất.
- Tạo ma trận: `Array.from({length: m}, () => new Array(n).fill(0))`. **Không** dùng `new Array(m).fill([])` vì mọi hàng sẽ trỏ chung một mảng.
- Destructuring swap: `[a, b] = [b, a]`.
- `BigInt` khi vượt `Number.MAX_SAFE_INTEGER` (2^53 − 1).
- Bitwise trong JS là 32-bit **signed**. Dùng `>>> 0` khi cần unsigned, `Math.trunc` thay vì `|0` với số lớn.
- Chia lấy nguyên: `Math.floor(a / b)` cho số dương, `Math.trunc(a / b)` khi có số âm.
- Modulo với số âm: `((a % m) + m) % m`.

### Những thứ JS không có sẵn (phải tự cài)
| Thiếu | Giải pháp |
|---|---|
| Priority Queue / Heap | Tự viết class MinHeap. **Bắt buộc thuộc lòng.** |
| Deque hiệu năng | `Array.shift()` là O(n). Dùng con trỏ `head` index, hoặc doubly linked list. |
| TreeMap / sorted set | Mảng đã sắp xếp + binary search, hoặc tự cài BST/Skip List. |
| Tuple làm key | Serialize thành string: `` `${r},${c}` ``. Với số nhỏ: `r * n + c`. |
| `defaultdict` | `map.set(k, (map.get(k) ?? 0) + 1)` |
| Counter | `for (const c of s) freq[c.charCodeAt(0) - 97]++` |

### Bẫy thường gặp
- Đệ quy sâu hơn ~10.000 sẽ stack overflow. Với cây/đồ thị lớn phải chuyển sang iterative.
- `for...in` duyệt **key** (kiểu string), `for...of` duyệt **value**.
- So sánh object/array bằng `===` là so sánh tham chiếu, không phải nội dung.
- `arr.splice(i, 1)` trong vòng lặp là O(n²), tránh dùng khi n lớn.
- `Number.MAX_SAFE_INTEGER` chỉ 2^53; các bài hash/tích lớn dễ mất chính xác.
- `[...arr]` là shallow copy. Mảng 2D cần `arr.map(row => [...row])`.

### Template cần chuẩn bị sẵn
> Viết một lần, thuộc lòng, dùng cả đời. Đây là việc nên làm trong Tuần 1–2.

1. [[Template - MinHeap trong JS]]
2. [[Template - Union-Find trong JS]]
3. [[Template - Trie trong JS]]
4. [[Template - Binary Search (lowerBound / upperBound)]]
5. [[Template - Binary Search on Answer]]
6. [[Template - Sliding Window (fixed & variable)]]
7. [[Template - Monotonic Stack]]
8. [[Template - Backtracking]]
9. [[Template - BFS trên grid (4 hướng & 8 hướng)]]
10. [[Template - Dijkstra]]
11. [[Template - Topological Sort (Kahn)]]
12. [[Template - Fenwick Tree]]
13. [[Template - Segment Tree]]
14. [[Template - Deque bằng con trỏ head]]
