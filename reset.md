## reset
```
working index HEAD target         working index HEAD
----------------------------------------------------
A       B     C    D     
                         --soft   A       B     D
                         --mixed  A       D     D
                         --hard   D       D     D
                         --merge (disallowed)
                         --keep  (disallowed)
```

```
working index HEAD target         working index HEAD
  ----------------------------------------------------
   A       B     C    C  
                         --soft   A       B     C
                         --mixed  A       C     C
                         --hard   C       C     C
                         --merge (disallowed)
                         --keep   A       C     C
```

```
working index HEAD target         working index HEAD
  ----------------------------------------------------
   B       B     C    D  
                         --soft   B       B     D
                         --mixed  B       D     D
                         --hard   D       D     D
                         --merge  D       D     D
                         --keep  (disallowed)
`````

```
working index HEAD target         working index HEAD
  ----------------------------------------------------
   B       B     C    C  
                         --soft   B       B     C
                         --mixed  B       C     C
                         --hard   C       C     C
                         --merge  C       C     C
                         --keep   B       C     C
```

```
working index HEAD target         working index HEAD
  ----------------------------------------------------
   B       C     C    D  
                         --soft   B       C     D
                         --mixed  B       D     D
                         --hard   D       D     D
                         --merge (disallowed)
                         --keep  (disallowed)
````

```
working index HEAD target         working index HEAD
  ----------------------------------------------------
   B       C     C    C  
                         --soft   B       C     C
                         --mixed  B       C     C
                         --hard   C       C     C
                         --merge  B       C     C
                         --keep   B       C     C
```

**ORIG_HEAD** is previous state of HEAD, set by commands that have possibly dangerous behavior, to be easy to revert them