# `diff` Command in Linux

`diff` is a command in Linux for comparing two files or directories and showing the differences.

## Syntax
```bash
$ diff reverseword1.js reverseword2.js
```

## Example

**reverseword1.js**
```javascript
function reversew(word){
let = result
for ( let i = wold.length -1 ; i >= 0 ; i--){
  result +=word[i]
}
  return result
}
console.log("ziko")
```

**reverseword2.js**
```javascript
function reversew(word){
# trim() function for remove space
word = word.trim()
let = result
for ( let i = wold.length -1 ; i >= 0 ; i--){
  result +=word[i]
}
  return result
}
console.log("ziko")
```

## Running the command
```bash
~$ diff reverseword1.js reverseword2.js
1a2,3
>     // trim() function for remove space
>     word = word.trim()
9d10
<
\ No newline at end of file
```

## `diff -u`
`diff -u` generates more context, which helps with reading and understanding the content (`-u` = unified format).

```bash
~$ diff -u reverseword1.js reverseword2.js
--- reverseword1.js     2026-08-20 01:15:46.349911605 +0100
+++ reverseword2.js     2026-08-20 01:16:47.156159546 +0100
@@ -1,4 +1,6 @@
 function reversew(word){
+    // trim() function for remove space
+    word = word.trim()
     let = result
     for ( let i = wold.length -1 ; i >= 0 ; i--){
       result +=word[i]
@@ -6,4 +8,3 @@
       return result
     }
     console.log("ziko")
-
\ No newline at end of file
```

## Resources
- [Diffing Files — Coursera](https://www.coursera.org/learn/introduction-git-github/lecture/tnlzg/diffing-files)
- [YouTube video](https://youtu.be/kXjB02U7W-o)
