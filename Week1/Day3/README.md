1. Sum of First N Numbers

Code:
public static int f(int n) {
  if (n == 0) return 0;
  return n + f(n - 1);
}
System.out.println(f(5));

Approach:
Add numbers from n to 1 using recursion.

Output:
15


2. Binary Representation Function

Code:
public static int foo(int n) {
  if (n == 1) return 1;
  if (n % 2 == 0) return 2 * foo(n / 2);
  return 2 * foo((n - 1) / 2) + 1;
}
System.out.println(foo(5));

Approach:
Converts number into binary and treats it as decimal. For 5 → binary 101 → value is 5.

Output:
5


3. Recursive Multiplication by Zero

Code:
public static int calc(int n) {
  if (n < 2) return n;
  return calc(n - 1) * calc(n - 2);
}
System.out.println(calc(5));

Approach:
Returns 0 for n ≥ 2 because calc(0) = 0 and multiplies everything.

Output:
0


4. GCD Using Euclidean Algorithm

Code:
public static int solve(int a, int b) {
  if (b == 0) return a;
  return solve(b, a % b);
}
System.out.println(solve(48, 18));

Approach:
Keep calling with (b, a % b) till b = 0.

Output:
6


5. Count Zeros in a Number

Code:
public static int solve(int n) {
  if (n == 0) return 1;
  if (n < 10) return 0;
  if (n % 10 == 0) return 1 + solve(n / 10);
  return solve(n / 10);
}
System.out.println(solve(102030));

Approach:
Check last digit is zero or not, then call for remaining number.

Output:
3


6. Longest Common Subsequence (LCS)

Code:
public static int solve(String X, String Y, int m, int n) {
  if (m == 0 || n == 0) return 0;
  if (X.charAt(m - 1) == Y.charAt(n - 1))
    return 1 + solve(X, Y, m - 1, n - 1);
  else
    return Math.max(solve(X, Y, m - 1, n), solve(X, Y, m, n - 1));
}
System.out.println(solve("AGGTAB", "GXTXAYB", 6, 7));

Approach:
Compare last characters. If match, +1. Else take max of two cases.

Output:
4


7. 0/1 Knapsack Problem

Code:
public static int solve(int[] masses, int[] merits, int limit, int n) {
  if (n == 0 || limit == 0) return 0;
  if (masses[n - 1] > limit)
    return solve(masses, merits, limit, n - 1);
  return Math.max(
    merits[n - 1] + solve(masses, merits, limit - masses[n - 1], n - 1),
    solve(masses, merits, limit, n - 1)
  );
}
int[] masses = {1, 3, 4, 5};
int[] merits = {1, 4, 5, 7};
System.out.println(solve(masses, merits, 7, 4));

Approach:
Include or exclude current item. Pick max merit.

Output:
9


8. Multiply Using Addition

Code:
public static int f(int a, int b) {
  if (b == 0) return 0;
  return a + f(a, b - 1);
}
System.out.println(f(3, 2));

Approach:
Add `a`, `b` times.

Output:
6


9. Complex Recursive Print

Code:
void recur(int n) {
  if (n <= 0) return;
  recur(n - 1);
  System.out.print(n);
  recur(n - 2);
}
recur(3);

Approach:
Prints after first recursion and before second.

Output:
1231


10. Unique Paths in a Grid

Code:
public static int countPaths(int m, int n) {
  if (m == 1 || n == 1) return 1;
  return countPaths(m - 1, n) + countPaths(m, n - 1);
}
System.out.println(countPaths(3, 3));

Approach:
Move either right or down. Add both paths.

Output:
6
