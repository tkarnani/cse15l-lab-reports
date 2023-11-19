# Lab Report 3
### CSE 15L 
### Tusha Karnani

---

## **Part 1**

### `reversed` method for arrays

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

---

## **Part 2**

### `grep` command

## -r to search for words in files recursively

**on a directory**

While in the `docsearch` directory, I used `grep -r` on the `technical` directory for the phrase "plausible range".

```
tushakarnani@Tushas-MacBook-Air-2 docsearch % grep -r "plausible range" technical
technical/plos/pmed.0020016.txt:         The regional models were calibrated as follows: first, plausible
					 ranges were specified
technical/biomed/1471-2288-3-9.txt:      no statement of uncertainty or a plausible range of
```

**on a file** 

While in the `docsearch` directory, I used `grep -r` on a file in the `technical` directory for the phrase "plausible range" (that I already knew contained the phrase).

```
tushakarnani@Tushas-MacBook-Air-2 docsearch % grep -r "plausible range" technical/plos/pmed.0020016.txt
technical/plos/pmed.0020016.txt:         The regional models were calibrated as follows: first, plausible
					 ranges were specified
```
