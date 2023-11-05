# Lab Report 3
### CSE 15L 
### Tusha Karnani

---

## **Part 1**

### 'reversed' method for arrays

**A failure inducing input**
```
@Test
	public void testReversed2() {
    int[] input1 = { 2, 3 };
    assertArrayEquals(new int[]{ 3, 2 }, ArrayExamples.reversed(input1));
  }
```

**An input that doesn't induce failure**
```
@Test
	public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
	}
```

**Symptoms - running JUnit tests**

![Image](s1.png)
![Image](s2.png)
![Image](s3.png)

**The bug**

This is the inital buggy code provided.

```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

The is the code after fixing the bug.

```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```

The code was initially adding elements from the new array into the old one instead of the other way around.
Changing the line of code inside the for loop to 'newArray[i] = arr[arr.length - i - 1];' and returning that array fixed the bug.
