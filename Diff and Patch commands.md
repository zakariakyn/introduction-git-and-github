# Working with `diff` and `patch`

After we get the file of changes using the command `diff -u`, we can apply these changes to our own file or project using the `patch` command. `patch` is used to update your original file by applying a `.diff` file.

## Syntax

The basic syntax is:
```bash
patch project_file < changes_file
```

### Applying a Patch

```bash
~$ patch reverseword1.js < changes.diff
patching file reverseword1.js
```

To check that `reverseword1.js` and `reverseword2.js` are now identical, run the `diff` command again. If the command returns nothing, the files match perfectly:

```bash
~$ diff -u reverseword1.js reverseword2.js
~$
```

## Reversing a Patch

Often, when updating our code, we might introduce a bug or the project might go down. When this happens, we need to recall (revert to) the previous version of the code. We can do this using the `-R` flag.

```bash
~$ patch -R reverseword1.js < changes.diff
patching file reverseword1.js
```

To verify that `reverseword1.js` is back to its previous version, you can run the `diff` command again to see the differences restored:

```diff
~$ diff -u reverseword1.js reverseword2.js
--- reverseword1.js     2026-08-20 01:15:46.349911605 +0100
+++ reverseword2.js     2026-08-20 01:16:47.156159546 +0100
@@ -1,4 +1,6 @@
 function reversew(word){
+    // trim() function for remove space
+    word = word.trim()
     let result = ""
     for ( let i = word.length - 1 ; i >= 0 ; i--){
       result += word[i]
@@ -6,4 +8,3 @@
       return result
     }
     console.log("ziko")
\ No newline at end of file
```

## Resources 
* [Coursera: Practical Application of diff and patch](https://www.coursera.org/learn/introduction-git-github/lecture/IkuqC/practical-application-of-diff-and-patch)
* [YouTube Resource](https://youtu.be/r9N-BOWWr-k)
