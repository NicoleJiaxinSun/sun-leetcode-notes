# Sliding Window

## Core Idea

Sliding window is about maintaining a valid range.

```text
[left ... right]
```

The window changes dynamically while scanning the array or string.

---

## Important Insight

The left pointer should never move backward.

Why:
- everything before left has already been processed
- moving backward breaks the window logic

---

## Longest Substring Without Repeating Characters

## Key Idea

Use:

```java
HashMap<Character, Integer>
```

Store:

```text
character -> latest index
```

When duplicate appears:

```java
left = Math.max(left, oldIndex + 1);
```

---

## Why Math.max Is Important

Without Math.max:
- left may move backward
- duplicate may re-enter the window

Math.max guarantees:

```text
left only moves forward
```

---

## Window Invariant

At every step:

```text
substring between left and right contains no duplicates
```

The entire algorithm depends on maintaining this invariant.

---

## My Learning Notes

At first, I thought:

```text
when duplicate appears,
just move left to duplicate + 1
```

But later I realized:
left may already be ahead.

So:

```java
left = Math.max(...)
```

is necessary.