# Binary Search

## Core Idea
- Binary search is not just to "find a number". The core idea is shrinking the search space.
- Remove the impossible side.

---

## Infinite Loop Warning

When using the `while (left < right)` binary search pattern, the search range must shrink every loop, otherwise an infinite loop may happen.

### Left-biased `mid`

```java
int mid = (left + right) / 2;
left = mid + 1;
right = mid;
```
- Left-biased `mid` may become equal to `left`,
  so we must move `left` to `mid + 1`.


### Right-biased `mid`

```java
int mid = (left + right + 1) / 2;
left = mid;
right = mid - 1;
```
- Right-biased `mid` may become equal to `right`,
  so we must move `right` to `mid - 1`.