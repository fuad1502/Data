Diffs are based on <span style="color:#1460aa">12,734</span> contexts (<span style="color:#1460aa">10,221</span> MinOpts, <span style="color:#1460aa">2,513</span> FullOpts).


<details>
<summary>Overall (<span style="color:green">-882,648</span> bytes)</summary>
<div style="margin-left:1em">

|Collection|Base size (bytes)|Diff size (bytes)|PerfScore in Diffs
|---|--:|--:|--:|
|test.mch|6,984,916|<span style="color:green">-882,648</span>|<span style="color:green">-1.62%</span>|


</div></details>

<details>
<summary>MinOpts (<span style="color:green">-684,524</span> bytes)</summary>
<div style="margin-left:1em">

|Collection|Base size (bytes)|Diff size (bytes)|PerfScore in Diffs
|---|--:|--:|--:|
|test.mch|5,347,656|<span style="color:green">-684,524</span>|<span style="color:green">-1.52%</span>|


</div></details>

<details>
<summary>FullOpts (<span style="color:green">-198,124</span> bytes)</summary>
<div style="margin-left:1em">

|Collection|Base size (bytes)|Diff size (bytes)|PerfScore in Diffs
|---|--:|--:|--:|
|test.mch|1,637,260|<span style="color:green">-198,124</span>|<span style="color:green">-2.06%</span>|


</div></details>

<details>
<summary>Example diffs</summary>
<div style="margin-left:1em">


<details>
<summary>test.mch</summary>
<div style="margin-left:1em">


<details>
<summary><span style="color:green">-48</span> (<span style="color:green">-38.71%</span>) : 198.dasm - System.ConsolePal:InvalidateCachedCursorPosition() (Tier0)</summary>
<div style="margin-left:1em">

```diff
@@ -19,36 +19,27 @@ G_M58234_IG01:        ; bbWeight=1, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref,
 						;; size=16 bbWeight=1 PerfScore 9.00
 G_M58234_IG02:        ; bbWeight=1, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
             addi           a0, zero, 0xD1FFAB1E
-            lui            a1, 0xD1FFAB1E
-            addiw          a1, a1, 0xD1FFAB1E
-            slli           a1, a1, 11
-            addi           a1, a1, 0xD1FFAB1E
-            slli           a1, a1, 5
-            addi           a1, a1, 0xD1FFAB1E
+            auipc          t6, 0xD1FFAB1E
+            ld             a1, 0xD1FFAB1E(t6)
             sw             a0, 0xD1FFAB1E(a1)
-            lui            a0, 0xD1FFAB1E
-            addiw          a0, a0, 0xD1FFAB1E
-            slli           a0, a0, 11
-            addi           a0, a0, 0xD1FFAB1E
-            slli           a0, a0, 5
-            addi           a0, a0, 0xD1FFAB1E
+            auipc          t6, 0xD1FFAB1E
+            ld             a0, 0xD1FFAB1E(t6)
             lw             a0, 0xD1FFAB1E(a0)
             addiw          a0, a0, 0xD1FFAB1E
-            lui            a1, 0xD1FFAB1E
-            addiw          a1, a1, 0xD1FFAB1E
-            slli           a1, a1, 11
-            addi           a1, a1, 0xD1FFAB1E
-            slli           a1, a1, 5
-            addi           a1, a1, 0xD1FFAB1E
+            auipc          t6, 0xD1FFAB1E
+            ld             a1, 0xD1FFAB1E(t6)
             sw             a0, 0xD1FFAB1E(a1)
-						;; size=92 bbWeight=1 PerfScore 20.00
+						;; size=44 bbWeight=1 PerfScore 17.00
 G_M58234_IG03:        ; bbWeight=1, epilog, nogc, extend
             ld             ra, 8(sp)
             ld             fp, 0(sp)
             addi           sp, sp, 16
             ret						;; size=16 bbWeight=1 PerfScore 7.50
+RWD00  	dq	00007E19B463B30Ch
+RWD08  	dq	00007E19B463B308h
 
-; Total bytes of code 124, prolog size 16, PerfScore 36.50, instruction count 31, allocated bytes for code 124 (MethodHash=d4221c85) for method System.ConsolePal:InvalidateCachedCursorPosition() (Tier0)
+
+; Total bytes of code 76, prolog size 16, PerfScore 33.50, instruction count 16, allocated bytes for code 76 (MethodHash=d4221c85) for method System.ConsolePal:InvalidateCachedCursorPosition() (Tier0)
 ; ============================================================
 
 Unwind Info:
@@ -59,7 +50,7 @@ Unwind Info:
   E bit             : 0
   X bit             : 0
   Vers              : 0
-  Function Length   : 31 (0x0001f) Actual length = 124 (0x00007c)
+  Function Length   : 19 (0x00013) Actual length = 76 (0x00004c)
   ---- Epilog scopes ----
   ---- Scope 0
   Epilog Start Offset        : 3523193630 (0xd1ffab1e) Actual offset = 3523193630 (0xd1ffab1e) Offset from main function begin = 3523193630 (0xd1ffab1e)
```

</div></details>

<details>
<summary><span style="color:green">-48</span> (<span style="color:green">-36.36%</span>) : 667.dasm - System.ConsolePal:InvalidateTerminalSettings() (FullOpts)</summary>
<div style="margin-left:1em">

```diff
@@ -23,38 +23,30 @@ G_M52800_IG01:        ; bbWeight=1, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref,
 						;; size=16 bbWeight=1 PerfScore 9.00
 G_M52800_IG02:        ; bbWeight=1, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
             addi           a0, fp, -16
-            lui            a1, 0xD1FFAB1E
-            addiw          a1, a1, 0xD1FFAB1E
-            slli           a1, a1, 11
-            addi           a1, a1, 0xD1FFAB1E
-            slli           a1, a1, 5
-            addi           a1, a1, 0xD1FFAB1E
+            auipc          t6, 0xD1FFAB1E
+            ld             a1, 0xD1FFAB1E(t6)
             jalr           a1		// CORINFO_HELP_JIT_REVERSE_PINVOKE_ENTER
             addi           a0, zero, 0xD1FFAB1E
-            lui            a1, 0xD1FFAB1E
-            addiw          a1, a1, 0xD1FFAB1E
-            slli           a1, a1, 11
-            addi           a1, a1, 0xD1FFAB1E
-            slli           a1, a1, 5
-            addi           a1, a1, 0xD1FFAB1E
+            auipc          t6, 0xD1FFAB1E
+            ld             a1, 0xD1FFAB1E(t6)
             fence          3, 3
             sw             a0, 0xD1FFAB1E(a1)
             addi           a0, fp, -16
-            lui            a1, 0xD1FFAB1E
-            addiw          a1, a1, 0xD1FFAB1E
-            slli           a1, a1, 11
-            addi           a1, a1, 0xD1FFAB1E
-            slli           a1, a1, 5
-            addi           a1, a1, 0xD1FFAB1E
+            auipc          t6, 0xD1FFAB1E
+            ld             a1, 0xD1FFAB1E(t6)
             jalr           a1		// CORINFO_HELP_JIT_REVERSE_PINVOKE_EXIT
-						;; size=100 bbWeight=1 PerfScore 25.50
+						;; size=52 bbWeight=1 PerfScore 22.50
 G_M52800_IG03:        ; bbWeight=1, epilog, nogc, extend
             ld             ra, 24(sp)
             ld             fp, 16(sp)
             addi           sp, sp, 32
             ret						;; size=16 bbWeight=1 PerfScore 7.50
+RWD00  	dq	00007E1A33AB9A74h
+RWD08  	dq	00007E19B463B31Ch
+RWD16  	dq	00007E1A33AB9BCCh
 
-; Total bytes of code 132, prolog size 16, PerfScore 42.00, instruction count 33, allocated bytes for code 132 (MethodHash=bc7731bf) for method System.ConsolePal:InvalidateTerminalSettings() (FullOpts)
+
+; Total bytes of code 84, prolog size 16, PerfScore 39.00, instruction count 18, allocated bytes for code 84 (MethodHash=bc7731bf) for method System.ConsolePal:InvalidateTerminalSettings() (FullOpts)
 ; ============================================================
 
 Unwind Info:
@@ -65,7 +57,7 @@ Unwind Info:
   E bit             : 0
   X bit             : 0
   Vers              : 0
-  Function Length   : 33 (0x00021) Actual length = 132 (0x000084)
+  Function Length   : 21 (0x00015) Actual length = 84 (0x000054)
   ---- Epilog scopes ----
   ---- Scope 0
   Epilog Start Offset        : 3523193630 (0xd1ffab1e) Actual offset = 3523193630 (0xd1ffab1e) Offset from main function begin = 3523193630 (0xd1ffab1e)
```

</div></details>

<details>
<summary><span style="color:green">-32</span> (<span style="color:green">-34.78%</span>) : 11911.dasm - Microsoft.CodeAnalysis.SyntaxNode+ChildSyntaxListEnumeratorStack+<>c:<.cctor>b__12_0():Microsoft.CodeAnalysis.ChildSyntaxList+Enumerator[]:this (Tier0)</summary>
<div style="margin-left:1em">

```diff
@@ -20,29 +20,24 @@ G_M43111_IG01:        ; bbWeight=1, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref,
             sd             a0, -8(fp)
 						;; size=20 bbWeight=1 PerfScore 13.00
 G_M43111_IG02:        ; bbWeight=1, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
-            lui            a0, 0xD1FFAB1E
-            addiw          a0, a0, 0xD1FFAB1E
-            slli           a0, a0, 11
-            addi           a0, a0, 0xD1FFAB1E
-            slli           a0, a0, 5
-            addi           a0, a0, 0xD1FFAB1E
+            auipc          t6, 0xD1FFAB1E
+            ld             a0, 0xD1FFAB1E(t6)
             addi           a1, zero, 0xD1FFAB1E
-            lui            a2, 0xD1FFAB1E
-            addiw          a2, a2, 0xD1FFAB1E
-            slli           a2, a2, 11
-            addi           a2, a2, 0xD1FFAB1E
-            slli           a2, a2, 5
-            addi           a2, a2, 0xD1FFAB1E
+            auipc          t6, 0xD1FFAB1E
+            ld             a2, 0xD1FFAB1E(t6)
             jalr           a2		// CORINFO_HELP_NEWARR_1_VC
             ; gcrRegs +[a0]
-						;; size=56 bbWeight=1 PerfScore 9.50
+						;; size=24 bbWeight=1 PerfScore 7.50
 G_M43111_IG03:        ; bbWeight=1, epilog, nogc, extend
             ld             ra, 24(sp)
             ld             fp, 16(sp)
             addi           sp, sp, 32
             ret						;; size=16 bbWeight=1 PerfScore 7.50
+RWD00  	dq	0000768AA9A1BFB8h
+RWD08  	dq	0000768B238B2044h
 
-; Total bytes of code 92, prolog size 16, PerfScore 30.00, instruction count 23, allocated bytes for code 92 (MethodHash=94ff5798) for method Microsoft.CodeAnalysis.SyntaxNode+ChildSyntaxListEnumeratorStack+<>c:<.cctor>b__12_0():Microsoft.CodeAnalysis.ChildSyntaxList+Enumerator[]:this (Tier0)
+
+; Total bytes of code 60, prolog size 16, PerfScore 28.00, instruction count 13, allocated bytes for code 60 (MethodHash=94ff5798) for method Microsoft.CodeAnalysis.SyntaxNode+ChildSyntaxListEnumeratorStack+<>c:<.cctor>b__12_0():Microsoft.CodeAnalysis.ChildSyntaxList+Enumerator[]:this (Tier0)
 ; ============================================================
 
 Unwind Info:
@@ -53,7 +48,7 @@ Unwind Info:
   E bit             : 0
   X bit             : 0
   Vers              : 0
-  Function Length   : 23 (0x00017) Actual length = 92 (0x00005c)
+  Function Length   : 15 (0x0000f) Actual length = 60 (0x00003c)
   ---- Epilog scopes ----
   ---- Scope 0
   Epilog Start Offset        : 3523193630 (0xd1ffab1e) Actual offset = 3523193630 (0xd1ffab1e) Offset from main function begin = 3523193630 (0xd1ffab1e)
```

</div></details>

<details>
<summary>+0 (0.00%) : 12720.dasm - System.Linq.Enumerable+EnumerableSorter`1[System.__Canon]:Sort(System.__Canon[],int):int[]:this (Tier0)</summary>
<div style="margin-left:1em">

```diff
@@ -33,9 +33,9 @@ G_M50207_IG02:        ; bbWeight=1, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
             lw             a2, -20(fp)
             lui            a3, 0xD1FFAB1E
             addiw          a3, a3, 0xD1FFAB1E
-            slli           a3, a3, 11
+            slli           a3, a3, 12
             addi           a3, a3, 0xD1FFAB1E
-            slli           a3, a3, 5
+            slli           a3, a3, 4
             ld             a3, 0xD1FFAB1E(a3)
             jalr           a3		// <unknown method>
             ; gcrRegs -[a1]
```

</div></details>

<details>
<summary>+0 (0.00%) : 12704.dasm - Microsoft.CodeAnalysis.CSharp.VariablesDeclaredWalker:Free():this (Tier0)</summary>
<div style="margin-left:1em">

```diff
@@ -24,9 +24,9 @@ G_M15256_IG02:        ; bbWeight=1, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
             ; gcrRegs +[a0]
             lui            a1, 0xD1FFAB1E
             addiw          a1, a1, 0xD1FFAB1E
-            slli           a1, a1, 11
+            slli           a1, a1, 14
             addi           a1, a1, 0xD1FFAB1E
-            slli           a1, a1, 5
+            slli           a1, a1, 2
             ld             a1, 0xD1FFAB1E(a1)
             jalr           a1		// <unknown method>
             ; gcrRegs -[a0]
```

</div></details>

<details>
<summary>+0 (0.00%) : 12640.dasm - Microsoft.CodeAnalysis.DiagnosticBag:Add(Microsoft.CodeAnalysis.Diagnostic):this (Tier0)</summary>
<div style="margin-left:1em">

```diff
@@ -28,9 +28,9 @@ G_M13912_IG02:        ; bbWeight=1, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
             ; gcrRegs +[a0]
             lui            a1, 0xD1FFAB1E
             addiw          a1, a1, 0xD1FFAB1E
-            slli           a1, a1, 11
+            slli           a1, a1, 14
             addi           a1, a1, 0xD1FFAB1E
-            slli           a1, a1, 5
+            slli           a1, a1, 2
             ld             a1, 0xD1FFAB1E(a1)
             jalr           a1		// <unknown method>
             sd             a0, -24(fp)
@@ -39,9 +39,9 @@ G_M13912_IG02:        ; bbWeight=1, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
             ; gcrRegs +[a1]
             lui            a2, 0xD1FFAB1E
             addiw          a2, a2, 0xD1FFAB1E
-            slli           a2, a2, 11
+            slli           a2, a2, 14
             addi           a2, a2, 0xD1FFAB1E
-            slli           a2, a2, 5
+            slli           a2, a2, 2
             ld             a2, 0xD1FFAB1E(a2)
             lw             zero, 0xD1FFAB1E(a0)
             jalr           a2		// <unknown method>
```

</div></details>


</div></details>


</div></details>

<details>
<summary>Details</summary>
<div style="margin-left:1em">

#### Size improvements/regressions per collection

|Collection|Contexts with diffs|Improvements|Regressions|Same size|Improvements (bytes)|Regressions (bytes)|
|---|--:|--:|--:|--:|--:|--:|
|test.mch|10,193|<span style="color:green">6,908</span>|<span style="color:red">0</span>|<span style="color:blue">3,285</span>|<span style="color:green">-882,648</span>|<span style="color:red">+0</span>|

---

#### PerfScore improvements/regressions per collection

|Collection|Contexts with diffs|Improvements|Regressions|Same PerfScore|Improvements (PerfScore)|Regressions (PerfScore)|PerfScore Overall in FullOpts|
|---|--:|--:|--:|--:|--:|--:|--:|
|test.mch|10,193|<span style="color:green">6,705</span>|<span style="color:red">0</span>|<span style="color:blue">3,488</span>|<span style="color:green">-2.46%</span>|0.00%|<span style="color:green">-1.6590%</span>|

---

#### Context information

|Collection|Diffed contexts|MinOpts|FullOpts|Missed, base|Missed, diff|
|---|--:|--:|--:|--:|--:|
|test.mch|12,734|10,221|2,513|0 (0.00%)|0 (0.00%)|


---

#### jit-analyze output


</div></details>

