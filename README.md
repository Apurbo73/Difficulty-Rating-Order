### Difficulty Rating Order



---

### 📌 **Objective:**

We are checking if students solved problems in **non-decreasing order** of difficulty — that means each difficulty should be **greater than or equal to** the previous one.

---

### 🔍 **Code Explanation:**

```cpp
int T;
cin >> T;
```

* This reads the number of **test cases** — i.e., how many student attempts you’ll be checking.

---

```cpp
while (T--) {
```

* A loop that runs once for each test case. `T--` decreases `T` each time until it reaches 0.

---

```cpp
int N;
cin >> N;
```

* Reads the number of problems the student solved.

---

```cpp
vector<int> difficulties(N);
for (int i = 0; i < N; ++i) {
    cin >> difficulties[i];
}
```

* Reads the `N` difficulty values into a vector.

---

```cpp
bool isNonDecreasing = true;
for (int i = 1; i < N; ++i) {
    if (difficulties[i] < difficulties[i - 1]) {
        isNonDecreasing = false;
        break;
    }
}
```

* We check from the **second element onward**.
* If at any point `difficulties[i] < difficulties[i - 1]`, that means the order is **decreasing**, which violates the rule.
* So we set `isNonDecreasing = false` and `break` out of the loop early.

---

```cpp
cout << (isNonDecreasing ? "Yes" : "No") << endl;
```

* Outputs "Yes" if the order was non-decreasing, otherwise "No".

---

### ✅ **Example Flow:**

**Input:**

```
1
5
1 2 2 3 4
```

* This student solved 5 problems with difficulty levels: 1 → 2 → 2 → 3 → 4
* All are non-decreasing (equal or increasing), so output is: `Yes`

---

The program starts by reading the number of test cases T. For each test case, it reads N, the number of problems the student solved, and then takes in N integers representing the difficulty of each problem.

It then checks if the sequence of difficulties is non-decreasing. This means it compares each difficulty with the one before it. If it ever finds a difficulty that is smaller than the previous one, it marks the sequence as invalid and stops checking.

Finally, if all difficulties were in non-decreasing order, it prints "Yes". Otherwise, it prints "No". This process repeats for each test case.
