Diffs are based on <span style="color:#1460aa">12,624</span> contexts (<span style="color:#1460aa">10,243</span> MinOpts, <span style="color:#1460aa">2,381</span> FullOpts).

<span style="color:#d35400">MISSED</span> contexts: base: <span style="color:green">0 (0.00%)</span>, diff: <span style="color:#d35400">2 (0.02%)</span>


<details>
<summary>Overall (<span style="color:green">-20,492</span> bytes)</summary>
<div style="margin-left:1em">

|Collection|Base size (bytes)|Diff size (bytes)|PerfScore in Diffs
|---|--:|--:|--:|
|test.mch|6,930,664|<span style="color:green">-20,492</span>|<span style="color:green">-0.48%</span>|


</div></details>

<details>
<summary>MinOpts (<span style="color:green">-7,496</span> bytes)</summary>
<div style="margin-left:1em">

|Collection|Base size (bytes)|Diff size (bytes)|PerfScore in Diffs
|---|--:|--:|--:|
|test.mch|5,385,844|<span style="color:green">-7,496</span>|<span style="color:green">-0.31%</span>|


</div></details>

<details>
<summary>FullOpts (<span style="color:green">-12,996</span> bytes)</summary>
<div style="margin-left:1em">

|Collection|Base size (bytes)|Diff size (bytes)|PerfScore in Diffs
|---|--:|--:|--:|
|test.mch|1,544,820|<span style="color:green">-12,996</span>|<span style="color:green">-0.69%</span>|


</div></details>

<details>
<summary>Example diffs</summary>
<div style="margin-left:1em">


<details>
<summary>test.mch</summary>
<div style="margin-left:1em">


<details>
<summary><span style="color:green">-12</span> (<span style="color:green">-12.00%</span>) : 3142.dasm - System.Collections.Immutable.ImmutableArray`1[System.__Canon]:get_Item(int):System.__Canon:this (Tier1)</summary>
<div style="margin-left:1em">

```diff
@@ -33,13 +33,11 @@ G_M52328_IG02:        ; bbWeight=1, gcrefRegs=0000 {}, byrefRegs=0400 {a0}, byre
             sext.w         a3, a1
             sext.w         a4, a2
             bgeu           a4, a3, G_M52328_IG04
-            slli           a1, a2, 32
-            srli           a1, a1, 32
-            slli           a1, a1, 3
-            add            a2, a0, a1
-            ; byrRegs +[a2]
-            ld             a0, 0xD1FFAB1E(a2)
-						;; size=40 bbWeight=1 PerfScore 12.50
+            sh3add.uw      a0, a2, a0
+            ; gcrRegs -[a0]
+            ld             a0, 0xD1FFAB1E(a0)
+            ; gcrRegs +[a0]
+						;; size=28 bbWeight=1 PerfScore 11.00
 G_M52328_IG03:        ; bbWeight=1, epilog, nogc, extend
             ld             ra, 8(sp)
             ld             fp, 0(sp)
@@ -47,7 +45,6 @@ G_M52328_IG03:        ; bbWeight=1, epilog, nogc, extend
             ret						;; size=16 bbWeight=1 PerfScore 7.50
 G_M52328_IG04:        ; bbWeight=0, gcVars=0000000000000000 {}, gcrefRegs=0000 {}, byrefRegs=0000 {}, gcvars, byref
             ; gcrRegs -[a0]
-            ; byrRegs -[a2]
             lui            a0, 0xD1FFAB1E
             addiw          a0, a0, 0xD1FFAB1E
             slli           a0, a0, 11
@@ -57,7 +54,7 @@ G_M52328_IG04:        ; bbWeight=0, gcVars=0000000000000000 {}, gcrefRegs=0000 {
             ebreak
 						;; size=28 bbWeight=0 PerfScore 0.00
 
-; Total bytes of code 100, prolog size 16, PerfScore 29.00, instruction count 25, allocated bytes for code 100 (MethodHash=cb333397) for method System.Collections.Immutable.ImmutableArray`1[System.__Canon]:get_Item(int):System.__Canon:this (Tier1)
+; Total bytes of code 88, prolog size 16, PerfScore 27.50, instruction count 22, allocated bytes for code 88 (MethodHash=cb333397) for method System.Collections.Immutable.ImmutableArray`1[System.__Canon]:get_Item(int):System.__Canon:this (Tier1)
 ; ============================================================
 
 Unwind Info:
@@ -68,7 +65,7 @@ Unwind Info:
   E bit             : 0
   X bit             : 0
   Vers              : 0
-  Function Length   : 25 (0x00019) Actual length = 100 (0x000064)
+  Function Length   : 22 (0x00016) Actual length = 88 (0x000058)
   ---- Epilog scopes ----
   ---- Scope 0
   Epilog Start Offset        : 3523193630 (0xd1ffab1e) Actual offset = 3523193630 (0xd1ffab1e) Offset from main function begin = 3523193630 (0xd1ffab1e)
```

</div></details>

<details>
<summary><span style="color:green">-12</span> (<span style="color:green">-11.54%</span>) : 3944.dasm - System.Collections.Immutable.ImmutableArray`1+Enumerator[System.__Canon]:get_Current():System.__Canon:this (Tier1)</summary>
<div style="margin-left:1em">

```diff
@@ -34,14 +34,10 @@ G_M46720_IG02:        ; bbWeight=1, gcrefRegs=0000 {}, byrefRegs=0400 {a0}, byre
             sext.w         a3, a2
             sext.w         a4, a0
             bgeu           a4, a3, G_M46720_IG04
-            slli           a0, a0, 32
-            srli           a0, a0, 32
-            slli           a0, a0, 3
-            add            a2, a1, a0
-            ; byrRegs +[a2]
-            ld             a0, 0xD1FFAB1E(a2)
+            sh3add.uw      a0, a0, a1
+            ld             a0, 0xD1FFAB1E(a0)
             ; gcrRegs +[a0]
-						;; size=44 bbWeight=1 PerfScore 14.50
+						;; size=32 bbWeight=1 PerfScore 13.00
 G_M46720_IG03:        ; bbWeight=1, epilog, nogc, extend
             ld             ra, 8(sp)
             ld             fp, 0(sp)
@@ -49,7 +45,6 @@ G_M46720_IG03:        ; bbWeight=1, epilog, nogc, extend
             ret						;; size=16 bbWeight=1 PerfScore 7.50
 G_M46720_IG04:        ; bbWeight=0, gcVars=0000000000000000 {}, gcrefRegs=0000 {}, byrefRegs=0000 {}, gcvars, byref
             ; gcrRegs -[a0-a1]
-            ; byrRegs -[a2]
             lui            a0, 0xD1FFAB1E
             addiw          a0, a0, 0xD1FFAB1E
             slli           a0, a0, 11
@@ -59,7 +54,7 @@ G_M46720_IG04:        ; bbWeight=0, gcVars=0000000000000000 {}, gcrefRegs=0000 {
             ebreak
 						;; size=28 bbWeight=0 PerfScore 0.00
 
-; Total bytes of code 104, prolog size 16, PerfScore 31.00, instruction count 26, allocated bytes for code 104 (MethodHash=ea0e497f) for method System.Collections.Immutable.ImmutableArray`1+Enumerator[System.__Canon]:get_Current():System.__Canon:this (Tier1)
+; Total bytes of code 92, prolog size 16, PerfScore 29.50, instruction count 23, allocated bytes for code 92 (MethodHash=ea0e497f) for method System.Collections.Immutable.ImmutableArray`1+Enumerator[System.__Canon]:get_Current():System.__Canon:this (Tier1)
 ; ============================================================
 
 Unwind Info:
@@ -70,7 +65,7 @@ Unwind Info:
   E bit             : 0
   X bit             : 0
   Vers              : 0
-  Function Length   : 26 (0x0001a) Actual length = 104 (0x000068)
+  Function Length   : 23 (0x00017) Actual length = 92 (0x00005c)
   ---- Epilog scopes ----
   ---- Scope 0
   Epilog Start Offset        : 3523193630 (0xd1ffab1e) Actual offset = 3523193630 (0xd1ffab1e) Offset from main function begin = 3523193630 (0xd1ffab1e)
```

</div></details>

<details>
<summary><span style="color:green">-32</span> (<span style="color:green">-10.13%</span>) : 323.dasm - NumericSortJagged:NumSift(int[],int,int) (Tier1)</summary>
<div style="margin-left:1em">

```diff
@@ -15,10 +15,10 @@
 ;  V04 loc1         [V04,T11] (  2, 16.07)     int  ->   a6        
 ;# V05 OutArgs      [V05    ] (  1,  1   )  struct ( 0) [sp+0x00]   do-not-enreg[XS] addr-exposed "OutgoingArgSpace" <Empty>
 ;  V06 tmp1         [V06,T04] (  2, 32.14)     int  ->   a5         "Strict ordering of exceptions for Array store"
-;  V07 cse0         [V07,T06] (  3, 24.57)     int  ->   a6         "CSE #07: aggressive"
-;  V08 cse1         [V08,T07] (  3, 24.57)     int  ->   a5         "CSE #12: aggressive"
-;  V09 cse2         [V09,T08] (  3, 24.57)    long  ->   a4         "CSE #05: aggressive"
-;  V10 cse3         [V10,T09] (  3, 24.57)    long  ->   a1         "CSE #10: aggressive"
+;  V07 cse0         [V07,T06] (  3, 24.57)     int  ->   a6         "CSE #06: aggressive"
+;  V08 cse1         [V08,T07] (  3, 24.57)     int  ->   a5         "CSE #10: aggressive"
+;  V09 cse2         [V09,T08] (  3, 24.57)    long  ->   a4         "CSE #04: aggressive"
+;  V10 cse3         [V10,T09] (  3, 24.57)    long  ->   a1         "CSE #08: aggressive"
 ;  V11 cse4         [V11,T02] (  6, 49.57)     int  ->   a4         multi-def "CSE #01: aggressive"
 ;  V12 cse5         [V12,T05] (  4, 29.17)     int  ->   a6         "CSE #02: aggressive"
 ;
@@ -60,34 +60,36 @@ G_M30577_IG06:        ; bbWeight=8.27, gcrefRegs=0400 {a0}, byrefRegs=0000 {}, b
             slli           a1, a1, 32
             srli           a1, a1, 32
             slli           a1, a1, 2
-            addi           a1, a1, 0xD1FFAB1E
-            add            t6, a0, a1
-            ; byrRegs +[t6]
-            lw             a5, 0xD1FFAB1E(t6)
+            add            a5, a0, a1
+            ; byrRegs +[a5]
+            lw             a5, 0xD1FFAB1E(a5)
+            ; byrRegs -[a5]
             sext.w         a6, a4
             sext.w         a7, a3
             bgeu           a7, a6, G_M30577_IG11
             slli           a4, a3, 32
             srli           a4, a4, 32
             slli           a4, a4, 2
-            addi           a4, a4, 0xD1FFAB1E
-            add            t6, a0, a4
-            lw             a6, 0xD1FFAB1E(t6)
+            add            a6, a0, a4
+            ; byrRegs +[a6]
+            lw             a6, 0xD1FFAB1E(a6)
+            ; byrRegs -[a6]
             slliw          ra, a5, 0
             slliw          t6, a6, 0
-            ; byrRegs -[t6]
             bge            ra, t6, G_M30577_IG04
-						;; size=88 bbWeight=8.27 PerfScore 202.53
+						;; size=80 bbWeight=8.27 PerfScore 194.27
 G_M30577_IG07:        ; bbWeight=8.04, gcrefRegs=0400 {a0}, byrefRegs=0000 {}, byref
-            add            t6, a0, a4
-            ; byrRegs +[t6]
-            sw             a5, 0xD1FFAB1E(t6)
-            add            t6, a0, a1
-            sw             a6, 0xD1FFAB1E(t6)
+            add            a4, a0, a4
+            ; byrRegs +[a4]
+            sw             a5, 0xD1FFAB1E(a4)
+            add            a1, a0, a1
+            ; byrRegs +[a1]
+            sw             a6, 0xD1FFAB1E(a1)
             sext.w         a1, a3
+            ; byrRegs -[a1]
 						;; size=20 bbWeight=8.04 PerfScore 76.34
 G_M30577_IG08:        ; bbWeight=8.27, gcrefRegs=0400 {a0}, byrefRegs=0000 {}, byref
-            ; byrRegs -[t6]
+            ; byrRegs -[a4]
             slliw          a3, a1, 1
             slliw          ra, a3, 0
             slliw          t6, a2, 0
@@ -104,31 +106,21 @@ G_M30577_IG10:        ; bbWeight=8.26, gcrefRegs=0400 {a0}, byrefRegs=0000 {}, b
             sext.w         a5, a4
             sext.w         a6, a3
             bgeu           a6, a5, G_M30577_IG11
-            slli           a5, a3, 32
-            srli           a5, a5, 32
-            slli           a5, a5, 2
-            add            a6, a0, a5
-            ; byrRegs +[a6]
-            lw             a5, 0xD1FFAB1E(a6)
+            sh2add.uw      a5, a3, a0
+            lw             a5, 0xD1FFAB1E(a5)
             addiw          a6, a3, 0xD1FFAB1E
-            ; byrRegs -[a6]
             sext.w         t0, a4
             sext.w         a7, a6
             bgeu           a7, t0, G_M30577_IG11
-            slli           a4, a6, 32
-            srli           a4, a4, 32
-            slli           a4, a4, 2
-            add            a7, a0, a4
-            ; byrRegs +[a7]
-            lw             a4, 0xD1FFAB1E(a7)
+            sh2add.uw      a4, a6, a0
+            lw             a4, 0xD1FFAB1E(a4)
             slliw          ra, a5, 0
             slliw          t6, a4, 0
             bge            ra, t6, G_M30577_IG06
             j              G_M30577_IG05
-						;; size=88 bbWeight=8.26 PerfScore 210.59
+						;; size=64 bbWeight=8.26 PerfScore 185.81
 G_M30577_IG11:        ; bbWeight=0, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
             ; gcrRegs -[a0]
-            ; byrRegs -[a7]
             lui            a0, 0xD1FFAB1E
             addiw          a0, a0, 0xD1FFAB1E
             slli           a0, a0, 11
@@ -139,7 +131,7 @@ G_M30577_IG11:        ; bbWeight=0, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
             ebreak
 						;; size=28 bbWeight=0 PerfScore 0.00
 
-; Total bytes of code 316, prolog size 16, PerfScore 596.28, instruction count 79, allocated bytes for code 316 (MethodHash=6405888e) for method NumericSortJagged:NumSift(int[],int,int) (Tier1)
+; Total bytes of code 284, prolog size 16, PerfScore 563.24, instruction count 71, allocated bytes for code 284 (MethodHash=6405888e) for method NumericSortJagged:NumSift(int[],int,int) (Tier1)
 ; ============================================================
 
 Unwind Info:
@@ -150,7 +142,7 @@ Unwind Info:
   E bit             : 0
   X bit             : 0
   Vers              : 0
-  Function Length   : 79 (0x0004f) Actual length = 316 (0x00013c)
+  Function Length   : 71 (0x00047) Actual length = 284 (0x00011c)
   ---- Epilog scopes ----
   ---- Scope 0
   Epilog Start Offset        : 3523193630 (0xd1ffab1e) Actual offset = 3523193630 (0xd1ffab1e) Offset from main function begin = 3523193630 (0xd1ffab1e)
```

</div></details>

<details>
<summary><span style="color:red">+8</span> (<span style="color:red">+0.49%</span>) : 631.dasm - EMFloatClass:Run():double:this (Tier1)</summary>
<div style="margin-left:1em">

```diff
@@ -30,10 +30,10 @@
 ;  V18 tmp10        [V18,T06] (  2, 668.27)     ref  ->   t4         class-hnd exact "NewArr temp" <<unknown class>>
 ;  V19 tmp11        [V19,T07] (  2, 668.27)     ref  ->   t4         class-hnd exact "NewArr temp" <<unknown class>>
 ;  V20 tmp12        [V20,T20] (  2,   0   )     ref  ->   a1         single-def "argument with side effect"
-;  V21 cse0         [V21,T04] (  4, 668.27)    long  ->   s8         "CSE #05: aggressive"
-;  V22 cse1         [V22,T15] (  4,   4   )    long  ->   s3         "CSE #02: aggressive"
+;  V21 cse0         [V21,T15] (  4,   4   )    long  ->   s3         "CSE #02: aggressive"
+;  V22 cse1         [V22,T04] (  4, 668.27)    long  ->   s8         "CSE #04: aggressive"
 ;  V23 cse2         [V23,T14] (  5, 171.07)     int  ->   s2         "CSE #01: aggressive"
-;  V24 cse3         [V24,T18] (  2,  65.29)  double  ->  fs7         hoist "CSE #06: aggressive"
+;  V24 cse3         [V24,T18] (  2,  65.29)  double  ->  fs7         hoist "CSE #05: aggressive"
 ;  V25 rat0         [V25,T11] (  3, 385.71)    long  ->   a0         "ReplaceWithLclVar is creating a new local variable"
 ;
 ; Lcl frame size = 0
@@ -176,10 +176,10 @@ G_M34029_IG03:        ; bbWeight=167.07, gcrefRegs=380200 {s1 s3 s4 s5}, byrefRe
             bgeu           t4, t0, G_M34029_IG16
             slli           t3, s6, 32
             srli           t3, t3, 32
-            slli           t3, t3, 3
-            addi           s8, t3, 0xD1FFAB1E
+            slli           s8, t3, 3
             add            t3, s4, s8
             ; byrRegs +[t3]
+            addi           t3, t3, 0xD1FFAB1E
             mv             t4, s7, 
             ; gcrRegs +[t4]
             lui            t2, 0xD1FFAB1E
@@ -249,6 +249,7 @@ G_M34029_IG03:        ; bbWeight=167.07, gcrefRegs=380200 {s1 s3 s4 s5}, byrefRe
             bgeu           t4, t0, G_M34029_IG16
             add            t3, s5, s8
             ; byrRegs +[t3]
+            addi           t3, t3, 0xD1FFAB1E
             mv             t4, s7, 
             ; gcrRegs +[t4]
             lui            t2, 0xD1FFAB1E
@@ -318,6 +319,7 @@ G_M34029_IG03:        ; bbWeight=167.07, gcrefRegs=380200 {s1 s3 s4 s5}, byrefRe
             bgeu           t4, t0, G_M34029_IG16
             add            t3, s3, s8
             ; byrRegs +[t3]
+            addi           t3, t3, 0xD1FFAB1E
             mv             t4, s7, 
             ; gcrRegs +[t4]
             lui            t2, 0xD1FFAB1E
@@ -334,7 +336,7 @@ G_M34029_IG03:        ; bbWeight=167.07, gcrefRegs=380200 {s1 s3 s4 s5}, byrefRe
             slliw          ra, s6, 0
             slliw          t6, s2, 0
             blt            ra, t6, G_M34029_IG03
-						;; size=692 bbWeight=167.07 PerfScore 30990.97
+						;; size=700 bbWeight=167.07 PerfScore 31158.04
 G_M34029_IG04:        ; bbWeight=1.00, gcrefRegs=380200 {s1 s3 s4 s5}, byrefRegs=0000 {}, byref
             sext.w         a3, s2
             mv             a0, s4, 
@@ -567,7 +569,7 @@ RWD00  	dq	3FF0000000000000h	;            1
 RWD08  	dq	408F400000000000h	;         1000
 
 
-; Total bytes of code 1628, prolog size 60, PerfScore 33424.09, instruction count 355, allocated bytes for code 1628 (MethodHash=bd287b12) for method EMFloatClass:Run():double:this (Tier1)
+; Total bytes of code 1636, prolog size 60, PerfScore 33591.16, instruction count 357, allocated bytes for code 1636 (MethodHash=bd287b12) for method EMFloatClass:Run():double:this (Tier1)
 ; ============================================================
 
 Unwind Info:
@@ -578,7 +580,7 @@ Unwind Info:
   E bit             : 0
   X bit             : 0
   Vers              : 0
-  Function Length   : 407 (0x00197) Actual length = 1628 (0x00065c)
+  Function Length   : 409 (0x00199) Actual length = 1636 (0x000664)
   ---- Epilog scopes ----
   ---- Scope 0
   Epilog Start Offset        : 3523193630 (0xd1ffab1e) Actual offset = 3523193630 (0xd1ffab1e) Offset from main function begin = 3523193630 (0xd1ffab1e)
```

</div></details>

<details>
<summary>+0 (0.00%) : 12432.dasm - Microsoft.CodeAnalysis.CSharp.Symbols.SymbolExtensions:GetTypeOrReturnType(Microsoft.CodeAnalysis.CSharp.Symbol,byref,byref,byref) (Tier0)</summary>
<div style="margin-left:1em">

No diffs found?

</div></details>

<details>
<summary>+0 (0.00%) : 11328.dasm - Microsoft.Cci.MetadataWriter:SerializePrimitiveType(System.Reflection.Metadata.Ecma335.CustomAttributeElementTypeEncoder,int) (Tier0)</summary>
<div style="margin-left:1em">

No diffs found?

</div></details>


</div></details>


</div></details>

<details>
<summary>Details</summary>
<div style="margin-left:1em">

#### Size improvements/regressions per collection

|Collection|Contexts with diffs|Improvements|Regressions|Same size|Improvements (bytes)|Regressions (bytes)|
|---|--:|--:|--:|--:|--:|--:|
|test.mch|1,454|<span style="color:green">830</span>|<span style="color:red">1</span>|<span style="color:blue">623</span>|<span style="color:green">-20,500</span>|<span style="color:red">+8</span>|

---

#### PerfScore improvements/regressions per collection

|Collection|Contexts with diffs|Improvements|Regressions|Same PerfScore|Improvements (PerfScore)|Regressions (PerfScore)|PerfScore Overall in FullOpts|
|---|--:|--:|--:|--:|--:|--:|--:|
|test.mch|1,454|<span style="color:green">783</span>|<span style="color:red">6</span>|<span style="color:blue">665</span>|<span style="color:green">-0.88%</span>|<span style="color:red">+0.41%</span>|<span style="color:green">-0.1819%</span>|

---

#### Context information

|Collection|Diffed contexts|MinOpts|FullOpts|Missed, base|Missed, diff|
|---|--:|--:|--:|--:|--:|
|test.mch|12,624|10,243|2,381|0 (0.00%)|2 (0.02%)|


---

#### jit-analyze output


</div></details>

