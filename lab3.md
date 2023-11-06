# Lab Report 3 - Bugs and Commands (Week 5)

## Part 1 - Bugs

In this section, we will examine a bug from the previous lab and provide the necessary tests, symptoms, and code corrections.

### Failure-Inducing Input

#### `reverseInPlace` Method Test

```java
@Test
public void testReverseInPlaceFailure() {
    int[] input = {1, 2, 3, 4};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int[]{4, 3, 2, 1}, input);
}
```

#### `reversed` Method Test

```java
@Test
public void testReversedFailure() {
    int[] input = {1, 2, 3, 4};
    int[] result = ArrayExamples.reversed(input);
    assertArrayEquals(new int[]{4, 3, 2, 1}, result);
}
```

### Non-Failure-Inducing Input

Given the nature of the bugs, most inputs will result in a failure. However, an array of length 1 will not:

#### `reverseInPlace` Method Test with Non-Failure Input

```java
@Test
public void testReverseInPlaceNonFailure() {
    int[] input = {1};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int[]{1}, input);
}
```

#### `reversed` Method Test with Non-Failure Input

```java
@Test
public void testReversedNonFailure() {
    int[] input = {1};
    int[] result = ArrayExamples.reversed(input);
    assertArrayEquals("A single-element array should be equal to itself when reversed", new int[]{1}, result);
}
```

### Symptom

![JUnit Test Output](URL_TO_IMAGE)

*Replace `URL_TO_IMAGE` with the actual URL to the screenshot of your JUnit test output.*

### The Bug and Fix

#### `reverseInPlace` Method

##### Before Fix

```java
// Buggy code block
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = arr[arr.length - i - 1];
  }
}
```

##### After Fix

```java
// Fixed code block
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length / 2; i += 1) {
    int temp = arr[i];
    arr[i] = arr[arr.length - i - 1];
    arr[arr.length - i - 1] = temp;
  }
}
```

#### `reversed` Method

##### Before Fix

```java
// Buggy code block
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = newArray[arr.length - i - 1];
  }
  return arr;
}
```

##### After Fix

```java
// Fixed code block
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    newArray[i] = arr[arr.length - i - 1];
  }
  return newArray;
}
```

### Explanation of the Fix

The `reverseInPlace` method's fix ensures that the swapping of elements is done correctly by only iterating up to the middle of the array and using a temporary variable to hold the value during the swap.

For the `reversed` method, the correction involves properly assigning the reversed values to a new array `newArray` and then returning this new array instead of the original, which remains unchanged.
```

Copy and paste this Markdown content into your `lab3.md` file on GitHub to incorporate it into your lab report. Be sure to add the screenshot of your JUnit test output where indicated.
