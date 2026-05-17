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


### Right-biased `mid`

```java
int mid = (left + right + 1) / 2;
left = mid;
right = mid - 1;
```

### Core Idea

Never keep the same boundary when `mid` can be equal to that boundary.
