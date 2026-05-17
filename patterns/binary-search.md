# Binary Search

## Core Idea

Binary search is not just to "find a number".
The core idea is shrinking the search space.
---

## Two Main Templates

### Exact Target Search

```java
while(left <= right)
```
- searching exact target

Key:
- must exclude mid
- left = mid + 1
- right = mid - 1

Reason:
mid has already been checked.

---

### Boundary Search

```java
while(left < right)
```
-  minimum/peak
-  first/last position
-  boundary

Key:
- sometimes keep mid


```java
right = mid;
```

or

```java
left = mid + 1;
```

Reason:
mid may still be the answer.

---

## Important Insight

The hardest part of binary search is not calculating mid.

The hardest part is:
- deciding whether to keep or exclude mid
- understanding what left/right represent
- understanding the meaning of the final pointer

---

## Mental Model


```text
Which side is definitely impossible?
```

Remove only the impossible side.

---

## Infinite Loop Warning

When using the `while (left < right)` binary search pattern, the search range must shrink every loop, otherwise an infinite loop may happen.

### Left-biased `mid`

```java
int mid = (left + right) / 2;
```

This `mid` is `left`biased.

So we should use:

```java
left = mid + 1;
right = mid;
```

and NOT:

```java
left = mid;
```
Because `mid` may equal `left`.


### Right-biased `mid`

```java
int mid = (left + right + 1) / 2;
```

This `mid` is `right`biased.

So we should use:

```java
left = mid;
right = mid - 1;
```

and NOT:

```java
right = mid;
```

Because `mid` may equal `right`.


### Core Idea

Never keep the same boundary when `mid` can be equal to that boundary.


---

## My Learning Notes

Boundary search usually keeps candidates.
Exact search removes checked candidates.