Diffs are based on <span style="color:#1460aa">12,755</span> contexts (<span style="color:#1460aa">10,245</span> MinOpts, <span style="color:#1460aa">2,510</span> FullOpts).


<details>
<summary>Overall (<span style="color:green">-10,180</span> bytes)</summary>
<div style="margin-left:1em">

|Collection|Base size (bytes)|Diff size (bytes)|PerfScore in Diffs
|---|--:|--:|--:|
|test.mch|6,984,808|<span style="color:green">-10,180</span>|<span style="color:green">-0.42%</span>|


</div></details>

<details>
<summary>MinOpts (<span style="color:green">-300</span> bytes)</summary>
<div style="margin-left:1em">

|Collection|Base size (bytes)|Diff size (bytes)|PerfScore in Diffs
|---|--:|--:|--:|
|test.mch|5,357,572|<span style="color:green">-300</span>|<span style="color:green">-0.03%</span>|


</div></details>

<details>
<summary>FullOpts (<span style="color:green">-9,880</span> bytes)</summary>
<div style="margin-left:1em">

|Collection|Base size (bytes)|Diff size (bytes)|PerfScore in Diffs
|---|--:|--:|--:|
|test.mch|1,627,236|<span style="color:green">-9,880</span>|<span style="color:green">-0.76%</span>|


</div></details>

<details>
<summary>Example diffs</summary>
<div style="margin-left:1em">


<details>
<summary>test.mch</summary>
<div style="margin-left:1em">


<details>
<summary><span style="color:green">-44</span> (<span style="color:green">-11.96%</span>) : 774.dasm - IDEAEncryption:en_key_idea(ushort[],ushort[]) (Tier1)</summary>
<div style="margin-left:1em">

```diff
@@ -47,10 +47,7 @@ G_M54750_IG03:        ; bbWeight=9.00, gcrefRegs=0C00 {a0 a1}, byrefRegs=0000 {}
             sext.w         t0, a5
             sext.w         a7, a2
             bgeu           a7, t0, G_M54750_IG07
-            slli           a2, a2, 32
-            srli           a2, a2, 32
-            slli           a2, a2, 1
-            add            a7, a0, a2
+            sh1add.uw      a7, a2, a0
             ; byrRegs +[a7]
             lhu            a2, 0xD1FFAB1E(a7)
             sext.w         a7, a4
@@ -61,8 +58,7 @@ G_M54750_IG03:        ; bbWeight=9.00, gcrefRegs=0C00 {a0 a1}, byrefRegs=0000 {}
             bgeu           t2, t1, G_M54750_IG07
             slli           a7, a7, 32
             srli           a7, a7, 32
-            slli           a7, a7, 1
-            add            t1, a1, a7
+            sh1add         t1, a7, a1
             ; byrRegs +[t1]
             sh             a2, 0xD1FFAB1E(t1)
             addiw          a4, a4, 0xD1FFAB1E
@@ -70,7 +66,7 @@ G_M54750_IG03:        ; bbWeight=9.00, gcrefRegs=0C00 {a0 a1}, byrefRegs=0000 {}
             sext.w         t6, a4
             addi           ra, zero, 0xD1FFAB1E
             blt            t6, ra, G_M54750_IG03
-						;; size=96 bbWeight=9.00 PerfScore 256.50
+						;; size=80 bbWeight=9.00 PerfScore 238.50
 G_M54750_IG04:        ; bbWeight=1.00, gcrefRegs=0800 {a1}, byrefRegs=0000 {}, byref
             ; gcrRegs -[a0]
             ; byrRegs -[t1]
@@ -86,10 +82,7 @@ G_M54750_IG05:        ; bbWeight=44.00, gcrefRegs=0800 {a1}, byrefRegs=0000 {},
             sext.w         a6, t0
             sext.w         a7, a5
             bgeu           a7, a6, G_M54750_IG07
-            slli           a5, a5, 32
-            srli           a5, a5, 32
-            slli           a5, a5, 1
-            add            a6, a1, a5
+            sh1add.uw      a6, a5, a1
             ; byrRegs +[a6]
             lhu            a5, 0xD1FFAB1E(a6)
             slliw          a5, a5, 9
@@ -100,10 +93,7 @@ G_M54750_IG05:        ; bbWeight=44.00, gcrefRegs=0800 {a1}, byrefRegs=0000 {},
             sext.w         t1, t0
             sext.w         a7, a6
             bgeu           a7, t1, G_M54750_IG07
-            slli           a6, a6, 32
-            srli           a6, a6, 32
-            slli           a6, a6, 1
-            add            a7, a1, a6
+            sh1add.uw      a7, a6, a1
             ; byrRegs +[a7]
             lhu            a6, 0xD1FFAB1E(a7)
             sraiw          a6, a6, 7
@@ -119,8 +109,7 @@ G_M54750_IG05:        ; bbWeight=44.00, gcrefRegs=0800 {a1}, byrefRegs=0000 {},
             bgeu           a7, t1, G_M54750_IG07
             slli           a6, a6, 32
             srli           a6, a6, 32
-            slli           a6, a6, 1
-            add            a7, a1, a6
+            sh1add         a7, a6, a1
             ; byrRegs +[a7]
             sh             a5, 0xD1FFAB1E(a7)
             andi           a0, a0, 0x8
@@ -130,7 +119,7 @@ G_M54750_IG05:        ; bbWeight=44.00, gcrefRegs=0800 {a1}, byrefRegs=0000 {},
             sext.w         t6, a4
             addi           ra, zero, 0xD1FFAB1E
             blt            t6, ra, G_M54750_IG05
-						;; size=180 bbWeight=44.00 PerfScore 1892.00
+						;; size=152 bbWeight=44.00 PerfScore 1738.00
 G_M54750_IG06:        ; bbWeight=1.00, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref, epilog, nogc
             ; gcrRegs -[a1]
             ; byrRegs -[a7]
@@ -149,7 +138,7 @@ G_M54750_IG07:        ; bbWeight=0, gcVars=0000000000000000 {}, gcrefRegs=0000 {
             ebreak
 						;; size=28 bbWeight=0 PerfScore 0.00
 
-; Total bytes of code 368, prolog size 16, PerfScore 2173.50, instruction count 92, allocated bytes for code 368 (MethodHash=49122a21) for method IDEAEncryption:en_key_idea(ushort[],ushort[]) (Tier1)
+; Total bytes of code 324, prolog size 16, PerfScore 2001.50, instruction count 81, allocated bytes for code 324 (MethodHash=49122a21) for method IDEAEncryption:en_key_idea(ushort[],ushort[]) (Tier1)
 ; ============================================================
 
 Unwind Info:
@@ -160,7 +149,7 @@ Unwind Info:
   E bit             : 0
   X bit             : 0
   Vers              : 0
-  Function Length   : 92 (0x0005c) Actual length = 368 (0x000170)
+  Function Length   : 81 (0x00051) Actual length = 324 (0x000144)
   ---- Epilog scopes ----
   ---- Scope 0
   Epilog Start Offset        : 3523193630 (0xd1ffab1e) Actual offset = 3523193630 (0xd1ffab1e) Offset from main function begin = 3523193630 (0xd1ffab1e)
```

</div></details>

<details>
<summary><span style="color:green">-12</span> (<span style="color:green">-11.54%</span>) : 4013.dasm - System.Collections.Immutable.ImmutableArray`1+Enumerator[System.__Canon]:get_Current():System.__Canon:this (Tier1)</summary>
<div style="margin-left:1em">

```diff
@@ -34,14 +34,11 @@ G_M46720_IG02:        ; bbWeight=1, gcrefRegs=0000 {}, byrefRegs=0400 {a0}, byre
             sext.w         a3, a2
             sext.w         a4, a0
             bgeu           a4, a3, G_M46720_IG04
-            slli           a0, a0, 32
-            srli           a0, a0, 32
-            slli           a0, a0, 3
-            add            a2, a1, a0
+            sh3add.uw      a2, a0, a1
             ; byrRegs +[a2]
             ld             a0, 0xD1FFAB1E(a2)
             ; gcrRegs +[a0]
-						;; size=44 bbWeight=1 PerfScore 14.50
+						;; size=32 bbWeight=1 PerfScore 13.00
 G_M46720_IG03:        ; bbWeight=1, epilog, nogc, extend
             ld             ra, 8(sp)
             ld             fp, 0(sp)
@@ -59,7 +56,7 @@ G_M46720_IG04:        ; bbWeight=0, gcVars=0000000000000000 {}, gcrefRegs=0000 {
             ebreak
 						;; size=28 bbWeight=0 PerfScore 0.00
 
-; Total bytes of code 104, prolog size 16, PerfScore 31.00, instruction count 26, allocated bytes for code 104 (MethodHash=ea0e497f) for method System.Collections.Immutable.ImmutableArray`1+Enumerator[System.__Canon]:get_Current():System.__Canon:this (Tier1)
+; Total bytes of code 92, prolog size 16, PerfScore 29.50, instruction count 23, allocated bytes for code 92 (MethodHash=ea0e497f) for method System.Collections.Immutable.ImmutableArray`1+Enumerator[System.__Canon]:get_Current():System.__Canon:this (Tier1)
 ; ============================================================
 
 Unwind Info:
@@ -70,7 +67,7 @@ Unwind Info:
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
<summary><span style="color:green">-12</span> (<span style="color:green">-8.57%</span>) : 874.dasm - System.IO.StringReader:Peek():int:this (Tier1)</summary>
<div style="margin-left:1em">

```diff
@@ -36,13 +36,10 @@ G_M61180_IG02:        ; bbWeight=1, gcrefRegs=0400 {a0}, byrefRegs=0000 {}, byre
             slli           t6, a0, 32
             srli           t6, t6, 32
             bgeu           t6, ra, G_M61180_IG05
-            slli           a0, a0, 32
-            srli           a0, a0, 32
-            slli           a0, a0, 1
-            add            a2, a1, a0
+            sh1add.uw      a2, a0, a1
             ; byrRegs +[a2]
             lhu            a0, 0xD1FFAB1E(a2)
-						;; size=56 bbWeight=1 PerfScore 20.00
+						;; size=44 bbWeight=1 PerfScore 18.50
 G_M61180_IG03:        ; bbWeight=1, epilog, nogc, extend
             ld             ra, 8(sp)
             ld             fp, 0(sp)
@@ -69,7 +66,7 @@ G_M61180_IG06:        ; bbWeight=0, epilog, nogc, extend
             addi           sp, sp, 16
             ret						;; size=16 bbWeight=0 PerfScore 0.00
 
-; Total bytes of code 140, prolog size 16, PerfScore 36.50, instruction count 35, allocated bytes for code 140 (MethodHash=73821103) for method System.IO.StringReader:Peek():int:this (Tier1)
+; Total bytes of code 128, prolog size 16, PerfScore 35.00, instruction count 32, allocated bytes for code 128 (MethodHash=73821103) for method System.IO.StringReader:Peek():int:this (Tier1)
 ; ============================================================
 
 Unwind Info:
@@ -80,7 +77,7 @@ Unwind Info:
   E bit             : 0
   X bit             : 0
   Vers              : 0
-  Function Length   : 35 (0x00023) Actual length = 140 (0x00008c)
+  Function Length   : 32 (0x00020) Actual length = 128 (0x000080)
   ---- Epilog scopes ----
   ---- Scope 0
   Epilog Start Offset        : 3523193630 (0xd1ffab1e) Actual offset = 3523193630 (0xd1ffab1e) Offset from main function begin = 3523193630 (0xd1ffab1e)
```

</div></details>

<details>
<summary><span style="color:red">+16</span> (<span style="color:red">+3.01%</span>) : 5070.dasm - System.Collections.Generic.ArraySortHelper`1[System.__Canon]:SwapIfGreater(System.Span`1[System.__Canon],System.Comparison`1[System.__Canon],int,int) (Instrumented Tier1)</summary>
<div style="margin-left:1em">

```diff
@@ -13,19 +13,17 @@
 ;* V00 TypeCtx      [V00    ] (  0,  0   )    long  ->  zero-ref    single-def
 ;* V01 arg0         [V01    ] (  0,  0   )  struct (16) zero-ref    multireg-arg ld-addr-op single-def <System.Span`1[System.__Canon]>
 ;  V02 arg1         [V02,T03] (  4,  4   )     ref  ->   s4         class-hnd single-def <System.Comparison`1[System.__Canon]>
-;  V03 arg2         [V03,T01] (  5,  5   )     int  ->   s2         single-def
-;  V04 arg3         [V04,T02] (  5,  5   )     int  ->   s3         single-def
-;  V05 loc0         [V05,T09] (  2,  1   )     ref  ->   a0         class-hnd single-def <System.__Canon>
+;  V03 arg2         [V03,T00] (  7,  6   )     int  ->   s1         single-def
+;  V04 arg3         [V04,T01] (  7,  6   )     int  ->   s2         single-def
+;  V05 loc0         [V05,T07] (  2,  1   )     ref  ->   a0         class-hnd single-def <System.__Canon>
 ;# V06 OutArgs      [V06    ] (  1,  1   )  struct ( 0) [sp+0x00]   do-not-enreg[XS] addr-exposed "OutgoingArgSpace" <Empty>
 ;* V07 tmp1         [V07    ] (  0,  0   )     ref  ->  zero-ref    single-def "handle histogram profile tmp"
 ;* V08 tmp2         [V08    ] (  0,  0   )   ubyte  ->  zero-ref    "Inlining Arg"
 ;* V09 tmp3         [V09    ] (  0,  0   )   ubyte  ->  zero-ref    "Inlining Arg"
-;  V10 tmp4         [V10,T00] (  7,  5   )   byref  ->   s1         single-def "field V01._reference (fldOffset=0x0)" P-INDEP
+;  V10 tmp4         [V10,T02] (  7,  5   )   byref  ->   s3         single-def "field V01._reference (fldOffset=0x0)" P-INDEP
 ;  V11 tmp5         [V11,T05] (  3,  3   )     int  ->   s5         single-def "field V01._length (fldOffset=0x8)" P-INDEP
 ;  V12 tmp6         [V12,T04] (  3,  6   )     ref  ->   s4         single-def "argument with side effect"
 ;  V13 tmp7         [V13,T06] (  2,  4   )     ref  ->   a1         single-def "argument with side effect"
-;  V14 cse0         [V14,T07] (  4,  3   )    long  ->   s2         "CSE #02: aggressive"
-;  V15 cse1         [V15,T08] (  4,  3   )    long  ->   s3         "CSE #04: aggressive"
 ;
 ; Lcl frame size = 8
 Frame info. #outsz=0; #framesz=64; lcl=8
@@ -40,20 +38,20 @@ G_M47099_IG01:        ; bbWeight=1, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref,
             sd             s4, 48(sp)
             sd             s5, 56(sp)
             addi           fp, sp, 8
-            mv             s1, a1, 
-            ; byrRegs +[s1]
+            mv             s3, a1, 
+            ; byrRegs +[s3]
             sext.w         s5, a2
             mv             s4, a3, 
             ; gcrRegs +[s4]
-            sext.w         s2, a4
-            sext.w         s3, a5
+            sext.w         s1, a4
+            sext.w         s2, a5
 						;; size=56 bbWeight=1 PerfScore 31.50
-G_M47099_IG02:        ; bbWeight=1, gcrefRegs=100000 {s4}, byrefRegs=0200 {s1}, byref
-            slliw          ra, s2, 0
-            slliw          t6, s3, 0
+G_M47099_IG02:        ; bbWeight=1, gcrefRegs=100000 {s4}, byrefRegs=80000 {s3}, byref
+            slliw          ra, s1, 0
+            slliw          t6, s2, 0
             bne            t6, ra, G_M47099_IG04
 						;; size=12 bbWeight=1 PerfScore 4.50
-G_M47099_IG03:        ; bbWeight=0.80, gcrefRegs=100000 {s4}, byrefRegs=0200 {s1}, byref
+G_M47099_IG03:        ; bbWeight=0.80, gcrefRegs=100000 {s4}, byrefRegs=80000 {s3}, byref
             lui            a0, 0xD1FFAB1E
             addiw          a0, a0, 0xD1FFAB1E
             slli           a0, a0, 11
@@ -72,7 +70,7 @@ G_M47099_IG03:        ; bbWeight=0.80, gcrefRegs=100000 {s4}, byrefRegs=0200 {s1
             ld             a2, 0xD1FFAB1E(a2)
             jalr           a2		// <unknown method>
 						;; size=68 bbWeight=0.80 PerfScore 10.00
-G_M47099_IG04:        ; bbWeight=1, gcrefRegs=100000 {s4}, byrefRegs=0200 {s1}, byref
+G_M47099_IG04:        ; bbWeight=1, gcrefRegs=100000 {s4}, byrefRegs=80000 {s3}, byref
             mv             a0, s4, 
             ; gcrRegs +[a0]
             lui            a1, 0xD1FFAB1E
@@ -90,22 +88,18 @@ G_M47099_IG04:        ; bbWeight=1, gcrefRegs=100000 {s4}, byrefRegs=0200 {s1},
             jalr           a2		// CORINFO_HELP_DELEGATEPROFILE32
             ; gcrRegs -[a0]
             sext.w         a1, s5
-            sext.w         a2, s2
+            sext.w         a2, s1
             bgeu           a2, a1, G_M47099_IG08
-            slli           a1, s2, 32
-            srli           a1, a1, 32
-            slli           s2, a1, 3
-            add            t6, s1, s2
+            mv             a1, s1, 
+            sh3add.uw      t6, a1, s3
             ; byrRegs +[t6]
             ld             a1, 0xD1FFAB1E(t6)
             ; gcrRegs +[a1]
             sext.w         a0, s5
-            sext.w         a2, s3
+            sext.w         a2, s2
             bgeu           a2, a0, G_M47099_IG08
-            slli           a2, s3, 32
-            srli           a2, a2, 32
-            slli           s3, a2, 3
-            add            t6, s1, s3
+            mv             a2, s2, 
+            sh3add.uw      t6, a2, s3
             ld             a2, 0xD1FFAB1E(t6)
             ; gcrRegs +[a2]
             ld             a0, 0xD1FFAB1E(s4)
@@ -116,8 +110,8 @@ G_M47099_IG04:        ; bbWeight=1, gcrefRegs=100000 {s4}, byrefRegs=0200 {s1},
             ; byrRegs -[t6]
             sext.w         t6, a0
             bge            zero, t6, G_M47099_IG06
-						;; size=140 bbWeight=1 PerfScore 37.50
-G_M47099_IG05:        ; bbWeight=0.50, gcrefRegs=0000 {}, byrefRegs=0200 {s1}, byref
+						;; size=124 bbWeight=1 PerfScore 35.50
+G_M47099_IG05:        ; bbWeight=0.50, gcrefRegs=0000 {}, byrefRegs=80000 {s3}, byref
             lui            a0, 0xD1FFAB1E
             addiw          a0, a0, 0xD1FFAB1E
             slli           a0, a0, 11
@@ -130,13 +124,20 @@ G_M47099_IG05:        ; bbWeight=0.50, gcrefRegs=0000 {}, byrefRegs=0200 {s1}, b
             slli           a1, a1, 5
             addi           a1, a1, 0xD1FFAB1E
             jalr           a1		// CORINFO_HELP_COUNTPROFILE32
-            add            t6, s1, s2
+            mv             t3, s1, 
+            sh3add.uw      t6, t3, s3
             ; byrRegs +[t6]
             ld             a0, 0xD1FFAB1E(t6)
             ; gcrRegs +[a0]
-            add            t3, s1, s2
+            slli           t3, s1, 32
+            srli           t3, t3, 32
+            slli           t4, t3, 3
+            ; byrRegs +[t4]
+            add            t3, s3, t4
             ; byrRegs +[t3]
-            add            t6, s1, s3
+            mv             t4, s2, 
+            ; byrRegs -[t4]
+            sh3add.uw      t6, t4, s3
             ld             t4, 0xD1FFAB1E(t6)
             ; gcrRegs +[t4]
             lui            t2, 0xD1FFAB1E
@@ -149,10 +150,15 @@ G_M47099_IG05:        ; bbWeight=0.50, gcrefRegs=0000 {}, byrefRegs=0200 {s1}, b
             jalr           ra, 0xD1FFAB1E(t2)		// CORINFO_HELP_CHECKED_ASSIGN_REF
             ; gcrRegs -[t4]
             ; byrRegs -[t3 t6]
-            add            t3, s1, s3
+            slli           t3, s2, 32
+            srli           t3, t3, 32
+            slli           t4, t3, 3
+            ; byrRegs +[t4]
+            add            t3, s3, t4
             ; byrRegs +[t3]
             mv             t4, a0, 
             ; gcrRegs +[t4]
+            ; byrRegs -[t4]
             lui            t2, 0xD1FFAB1E
             addi           t2, t2, 0xD1FFAB1E
             slli           t2, t2, 11
@@ -162,8 +168,8 @@ G_M47099_IG05:        ; bbWeight=0.50, gcrefRegs=0000 {}, byrefRegs=0200 {s1}, b
             slli           t2, t2, 10
             jalr           ra, 0xD1FFAB1E(t2)		// CORINFO_HELP_CHECKED_ASSIGN_REF
             ; gcrRegs -[a0 t4]
-            ; byrRegs -[s1 t3]
-						;; size=140 bbWeight=0.50 PerfScore 17.50
+            ; byrRegs -[s3 t3]
+						;; size=172 bbWeight=0.50 PerfScore 19.50
 G_M47099_IG06:        ; bbWeight=1, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
             lui            a0, 0xD1FFAB1E
             addiw          a0, a0, 0xD1FFAB1E
@@ -199,7 +205,7 @@ G_M47099_IG08:        ; bbWeight=0, gcVars=0000000000000000 {}, gcrefRegs=0000 {
             ebreak
 						;; size=28 bbWeight=0 PerfScore 0.00
 
-; Total bytes of code 532, prolog size 36, PerfScore 127.50, instruction count 119, allocated bytes for code 532 (MethodHash=50934804) for method System.Collections.Generic.ArraySortHelper`1[System.__Canon]:SwapIfGreater(System.Span`1[System.__Canon],System.Comparison`1[System.__Canon],int,int) (Instrumented Tier1)
+; Total bytes of code 548, prolog size 36, PerfScore 127.50, instruction count 123, allocated bytes for code 548 (MethodHash=50934804) for method System.Collections.Generic.ArraySortHelper`1[System.__Canon]:SwapIfGreater(System.Span`1[System.__Canon],System.Comparison`1[System.__Canon],int,int) (Instrumented Tier1)
 ; ============================================================
 
 Unwind Info:
@@ -210,7 +216,7 @@ Unwind Info:
   E bit             : 0
   X bit             : 0
   Vers              : 0
-  Function Length   : 133 (0x00085) Actual length = 532 (0x000214)
+  Function Length   : 137 (0x00089) Actual length = 548 (0x000224)
   ---- Epilog scopes ----
   ---- Scope 0
   Epilog Start Offset        : 3523193630 (0xd1ffab1e) Actual offset = 3523193630 (0xd1ffab1e) Offset from main function begin = 3523193630 (0xd1ffab1e)
```

</div></details>

<details>
<summary><span style="color:red">+4</span> (<span style="color:red">+0.50%</span>) : 343.dasm - System.SpanHelpers:IndexOfNullCharacter(ulong):int (Instrumented Tier1)</summary>
<div style="margin-left:1em">

```diff
@@ -10,8 +10,8 @@
 ; Final local variable assignments
 ;
 ;  V00 arg0         [V00,T00] (  8,  4.96)    long  ->   s1         single-def
-;  V01 loc0         [V01,T01] ( 11,  3.18)    long  ->   s2        
-;  V02 loc1         [V02,T03] (  7,  1.26)    long  ->   s3        
+;  V01 loc0         [V01,T01] ( 14,  4.09)    long  ->   s2        
+;  V02 loc1         [V02,T02] (  7,  1.26)    long  ->   s3        
 ;* V03 loc2         [V03    ] (  0,  0   )     ref  ->  zero-ref    class-hnd <<unknown class>>
 ;* V04 loc3         [V04    ] (  0,  0   )     ref  ->  zero-ref    class-hnd <<unknown class>>
 ;* V05 loc4         [V05    ] (  0,  0   )     ref  ->  zero-ref    class-hnd <<unknown class>>
@@ -36,7 +36,6 @@
 ;* V24 tmp2         [V24    ] (  0,  0   )    long  ->  zero-ref    "field V19._upper (fldOffset=0x8)" P-INDEP
 ;* V25 tmp3         [V25    ] (  0,  0   )    long  ->  zero-ref    "field V20._lower (fldOffset=0x0)" P-INDEP
 ;* V26 tmp4         [V26    ] (  0,  0   )    long  ->  zero-ref    "field V20._upper (fldOffset=0x8)" P-INDEP
-;  V27 cse0         [V27,T02] (  5,  2.97)    long  ->   a0         "CSE #01: moderate"
 ;
 ; Lcl frame size = 8
 Frame info. #outsz=0; #framesz=48; lcl=8
@@ -76,30 +75,32 @@ G_M54480_IG03:        ; bbWeight=0.50, gcrefRegs=0000 {}, byrefRegs=0000 {}, byr
             ; gcr arg pop 0
 						;; size=52 bbWeight=0.50 PerfScore 4.50
 G_M54480_IG04:        ; bbWeight=1.03, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
-            slli           a0, s2, 1
-            add            t6, s1, a0
-            lhu            a1, 0xD1FFAB1E(t6)
-            sext.w         t6, a1
+            sh1add         t6, s2, s1
+            lhu            a0, 0xD1FFAB1E(t6)
+            sext.w         t6, a0
             beqz           t6, G_M54480_IG11
-						;; size=20 bbWeight=1.03 PerfScore 8.26
+						;; size=16 bbWeight=1.03 PerfScore 7.74
 G_M54480_IG05:        ; bbWeight=0.52, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
-            add            a1, s1, a0
-            lhu            a1, 0xD1FFAB1E(a1)
-            sext.w         t6, a1
+            slli           a0, s2, 1
+            add            a0, s1, a0
+            lhu            a0, 0xD1FFAB1E(a0)
+            sext.w         t6, a0
             beqz           t6, G_M54480_IG14
-						;; size=16 bbWeight=0.52 PerfScore 3.87
+						;; size=20 bbWeight=0.52 PerfScore 4.13
 G_M54480_IG06:        ; bbWeight=0.26, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
-            add            a1, s1, a0
-            lhu            a1, 0xD1FFAB1E(a1)
-            sext.w         t6, a1
+            slli           a0, s2, 1
+            add            a0, s1, a0
+            lhu            a0, 0xD1FFAB1E(a0)
+            sext.w         t6, a0
             beqz           t6, G_M54480_IG16
-						;; size=16 bbWeight=0.26 PerfScore 1.94
+						;; size=20 bbWeight=0.26 PerfScore 2.06
 G_M54480_IG07:        ; bbWeight=0.13, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
+            slli           a0, s2, 1
             add            a0, s1, a0
             lhu            a0, 0xD1FFAB1E(a0)
             sext.w         t6, a0
             beqz           t6, G_M54480_IG18
-						;; size=16 bbWeight=0.13 PerfScore 0.97
+						;; size=20 bbWeight=0.13 PerfScore 1.03
 G_M54480_IG08:        ; bbWeight=0.06, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
             lui            a0, 0xD1FFAB1E
             addiw          a0, a0, 0xD1FFAB1E
@@ -265,12 +266,11 @@ G_M54480_IG19:        ; bbWeight=0.06, epilog, nogc, extend
             addi           sp, sp, 48
             ret						;; size=28 bbWeight=0.06 PerfScore 0.87
 G_M54480_IG20:        ; bbWeight=0.02, gcVars=0000000000000000 {}, gcrefRegs=0000 {}, byrefRegs=0000 {}, gcvars, byref
-            slli           a0, s2, 1
-            add            t6, s1, a0
+            sh1add         t6, s2, s1
             lhu            a0, 0xD1FFAB1E(t6)
             sext.w         t6, a0
             beqz           t6, G_M54480_IG12
-						;; size=20 bbWeight=0.02 PerfScore 0.17
+						;; size=16 bbWeight=0.02 PerfScore 0.16
 G_M54480_IG21:        ; bbWeight=0.01, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
             lui            a0, 0xD1FFAB1E
             addiw          a0, a0, 0xD1FFAB1E
@@ -290,7 +290,7 @@ G_M54480_IG21:        ; bbWeight=0.01, gcrefRegs=0000 {}, byrefRegs=0000 {}, byr
             j              G_M54480_IG09
 						;; size=60 bbWeight=0.01 PerfScore 0.12
 
-; Total bytes of code 800, prolog size 32, PerfScore 76.29, instruction count 200, allocated bytes for code 800 (MethodHash=e0692b2f) for method System.SpanHelpers:IndexOfNullCharacter(ulong):int (Instrumented Tier1)
+; Total bytes of code 804, prolog size 32, PerfScore 76.22, instruction count 201, allocated bytes for code 804 (MethodHash=e0692b2f) for method System.SpanHelpers:IndexOfNullCharacter(ulong):int (Instrumented Tier1)
 ; ============================================================
 
 Unwind Info:
@@ -301,7 +301,7 @@ Unwind Info:
   E bit             : 0
   X bit             : 0
   Vers              : 0
-  Function Length   : 200 (0x000c8) Actual length = 800 (0x000320)
+  Function Length   : 201 (0x000c9) Actual length = 804 (0x000324)
   ---- Epilog scopes ----
   ---- Scope 0
   Epilog Start Offset        : 3523193630 (0xd1ffab1e) Actual offset = 3523193630 (0xd1ffab1e) Offset from main function begin = 3523193630 (0xd1ffab1e)
```

</div></details>

<details>
<summary><span style="color:red">+12</span> (<span style="color:red">+0.47%</span>) : 580.dasm - EMFloat:DivideInternalFPF(byref,byref,byref) (Tier1)</summary>
<div style="margin-left:1em">

```diff
@@ -9,11 +9,11 @@
 ; 9 inlinees with PGO data; 2 single block inlinees; 0 inlinees without PGO data
 ; Final local variable assignments
 ;
-;  V00 arg0         [V00,T45] ( 12,  11   )   byref  ->   s3         single-def
+;  V00 arg0         [V00,T44] ( 12,  11   )   byref  ->   s3         single-def
 ;  V01 arg1         [V01,T26] ( 14, 278.66)   byref  ->   s2         single-def
 ;  V02 arg2         [V02,T24] ( 31, 401.66)   byref  ->   s1         single-def
-;  V03 loc0         [V03,T34] (  6,  26.01)     int  ->   a1        
-;  V04 loc1         [V04,T16] ( 12,1176.58)     int  ->   a2        
+;  V03 loc0         [V03,T33] (  6,  26.01)     int  ->   a1        
+;  V04 loc1         [V04,T16] ( 13,1191.39)     int  ->   a2        
 ;  V05 loc2         [V05,T00] ( 15,4598.67)  ushort  ->   a1         ld-addr-op
 ;  V06 loc3         [V06,T11] (  8,1741.37)    long  ->   s4         class-hnd exact single-def <ushort[]>
 ;* V07 loc4         [V07    ] (  0,   0   )  struct (16) zero-ref    ld-addr-op <EMFloat+InternalFPF>
@@ -23,14 +23,14 @@
 ;* V11 tmp1         [V11    ] (  0,   0   )    long  ->  zero-ref    class-hnd exact "NewArr temp" <ushort[]>
 ;  V12 tmp2         [V12,T19] (  3, 769.31)   byref  ->   a1         "dup spill"
 ;* V13 tmp3         [V13    ] (  0,   0   )     ref  ->  zero-ref    class-hnd exact "NewArr temp" <ushort[]>
-;  V14 tmp4         [V14,T35] (  6,  26.00)     int  ->   a1         "Inline stloc first use temp"
-;  V15 tmp5         [V15,T36] (  2,  20.00)     int  ->   a2         "Strict ordering of exceptions for Array store"
-;  V16 tmp6         [V16,T48] (  4,  12.07)     int  ->   a1         "Inline stloc first use temp"
-;* V17 tmp7         [V17,T58] (  0,   0   )     int  ->  zero-ref    "Inline stloc first use temp"
-;* V18 tmp8         [V18,T55] (  0,   0   )     ref  ->  zero-ref    class-hnd single-def "Inlining Arg" <ushort[]>
-;  V19 tmp9         [V19,T46] (  6,  12.07)     int  ->   a2         "Inline stloc first use temp"
-;  V20 tmp10        [V20,T56] (  6,   1.50)     int  ->   a3         "Inline stloc first use temp"
-;  V21 tmp11        [V21,T49] (  6,   8.34)     ref  ->   a1         class-hnd single-def "Inlining Arg" <ushort[]>
+;  V14 tmp4         [V14,T34] (  6,  26.00)     int  ->   a1         "Inline stloc first use temp"
+;  V15 tmp5         [V15,T35] (  2,  20.00)     int  ->   a2         "Strict ordering of exceptions for Array store"
+;  V16 tmp6         [V16,T47] (  4,  12.07)     int  ->   a1         "Inline stloc first use temp"
+;* V17 tmp7         [V17,T57] (  0,   0   )     int  ->  zero-ref    "Inline stloc first use temp"
+;* V18 tmp8         [V18,T54] (  0,   0   )     ref  ->  zero-ref    class-hnd single-def "Inlining Arg" <ushort[]>
+;  V19 tmp9         [V19,T45] (  6,  12.07)     int  ->   a2         "Inline stloc first use temp"
+;  V20 tmp10        [V20,T55] (  6,   1.50)     int  ->   a3         "Inline stloc first use temp"
+;  V21 tmp11        [V21,T48] (  6,   8.34)     ref  ->   a1         class-hnd single-def "Inlining Arg" <ushort[]>
 ;  V22 tmp12        [V22,T06] (  5,2698.53)     int  ->   a2         "Inline stloc first use temp"
 ;* V23 tmp13        [V23,T27] (  0,   0   )     ref  ->  zero-ref    class-hnd "Inlining Arg" <ushort[]>
 ;  V24 tmp14        [V24,T03] (  7,3310.87)  ushort  ->   a4         "Inline stloc first use temp"
@@ -46,13 +46,13 @@
 ;  V34 tmp24        [V34,T01] (  9,3367.73)     ref  ->   a2         class-hnd "Inlining Arg" <ushort[]>
 ;  V35 tmp25        [V35,T02] ( 14,3310.87)  ushort  ->   a5         "Inline stloc first use temp"
 ;  V36 tmp26        [V36,T13] (  4,1285.16)     int  ->   a6         "Inline stloc first use temp"
-;  V37 tmp27        [V37,T51] (  3,   6.00)   byref  ->   a1         single-def "dup spill"
-;  V38 tmp28        [V38,T54] (  7,   2.00)     int  ->   a1         "Inline stloc first use temp"
-;  V39 tmp29        [V39,T59] (  3,   0   )   byref  ->   a0         single-def "dup spill"
-;  V40 tmp30        [V40,T60] (  3,   0   )     ref  ->   s1         class-hnd exact single-def "NewObj constructor temp" <<unknown class>>
-;  V41 tmp31        [V41,T47] (  6,  12.07)     int  ->   a1         "Inline stloc first use temp"
-;  V42 tmp32        [V42,T57] (  6,   1.50)     int  ->   a2         "Inline stloc first use temp"
-;  V43 tmp33        [V43,T50] (  6,   8.34)     ref  ->   a0         class-hnd single-def "Inlining Arg" <ushort[]>
+;  V37 tmp27        [V37,T50] (  3,   6.00)   byref  ->   a1         single-def "dup spill"
+;  V38 tmp28        [V38,T53] (  7,   2.00)     int  ->   a1         "Inline stloc first use temp"
+;  V39 tmp29        [V39,T58] (  3,   0   )   byref  ->   a0         single-def "dup spill"
+;  V40 tmp30        [V40,T59] (  3,   0   )     ref  ->   s1         class-hnd exact single-def "NewObj constructor temp" <<unknown class>>
+;  V41 tmp31        [V41,T46] (  6,  12.07)     int  ->   a1         "Inline stloc first use temp"
+;  V42 tmp32        [V42,T56] (  6,   1.50)     int  ->   a2         "Inline stloc first use temp"
+;  V43 tmp33        [V43,T49] (  6,   8.34)     ref  ->   a0         class-hnd single-def "Inlining Arg" <ushort[]>
 ;  V44 tmp34        [V44    ] (  3,   3   )  struct (24) [fp-0x18]   do-not-enreg[XS] must-init addr-exposed "stack allocated array temp" <ushort[]>
 ;  V45 tmp35        [V45,T12] (  5,1292.16)     ref  ->   a0         single-def "field V07.mantissa (fldOffset=0x0)" P-INDEP
 ;* V46 tmp36        [V46    ] (  0,   0   )   short  ->  zero-ref    "field V07.exp (fldOffset=0x8)" P-INDEP
@@ -62,27 +62,26 @@
 ;  V50 tmp40        [V50,T31] (  3,  30.01)     ref  ->   a2         "arr expr"
 ;  V51 tmp41        [V51,T18] (  3, 775.31)     ref  ->   a1         "arr expr"
 ;  V52 tmp42        [V52,T20] (  3, 659.65)     ref  ->   a3         "arr expr"
-;* V53 tmp43        [V53,T33] (  0,   0   )     ref  ->  zero-ref    "arr expr"
+;  V53 tmp43        [V53,T29] (  3,  88.87)     ref  ->   a3         "arr expr"
 ;  V54 tmp44        [V54,T17] (  3, 976.38)     ref  ->   a6         "arr expr"
-;  V55 tmp45        [V55,T52] (  3,   6.00)     ref  ->   a1         single-def "arr expr"
-;  V56 tmp46        [V56,T61] (  2,   0   )     ref  ->   a1         single-def "argument with side effect"
-;  V57 cse0         [V57,T28] (  3, 234.69)     int  ->   a3         "CSE #29: moderate"
-;  V58 cse1         [V58,T08] (  3,1927.73)    long  ->   a3         "CSE #15: aggressive"
-;  V59 cse2         [V59,T10] (  3,1889.37)    long  ->   a4         "CSE #44: aggressive"
-;  V60 cse3         [V60,T30] (  3,  38.36)    long  ->   a4         "CSE #48: moderate"
-;  V61 cse4         [V61,T44] (  3,  15.00)    long  ->   a3         "CSE #03: moderate"
-;  V62 cse5         [V62,T09] (  3,1927.73)    long  ->   a3         "CSE #20: aggressive"
-;  V63 cse6         [V63,T21] (  4, 650.92)    long  ->   a3         "CSE #39: moderate"
-;  V64 cse7         [V64,T25] (  4, 344.64)    long  ->   a4         "CSE #25: moderate"
-;  V65 cse8         [V65,T43] (  3,  15.01)    long  ->   a3         "CSE #10: moderate"
-;  V66 cse9         [V66,T29] (  2, 219.87)     ref  ->   a1         hoist "CSE #23: moderate"
-;  V67 rat0         [V67,T37] (  4,  16.10)   byref  ->   a2         "Strength reduced derived IV"
-;  V68 rat1         [V68,T38] (  4,  16.10)     int  ->   a3         "Trip count IV"
-;  V69 rat2         [V69,T39] (  4,  15.78)   byref  ->   a1         "Strength reduced derived IV"
-;  V70 rat3         [V70,T41] (  4,  15.78)     int  ->   a3         "Trip count IV"
-;  V71 rat4         [V71,T40] (  4,  15.78)   byref  ->   a0         "Strength reduced derived IV"
-;  V72 rat5         [V72,T42] (  4,  15.78)     int  ->   a2         "Trip count IV"
-;  V73 rat6         [V73,T53] (  3,   6   )     int  ->   a0         "ReplaceWithLclVar is creating a new local variable"
+;  V55 tmp45        [V55,T51] (  3,   6.00)     ref  ->   a1         single-def "arr expr"
+;  V56 tmp46        [V56,T60] (  2,   0   )     ref  ->   a1         single-def "argument with side effect"
+;  V57 cse0         [V57,T08] (  3,1927.73)    long  ->   a3         "CSE #15: aggressive"
+;  V58 cse1         [V58,T10] (  3,1889.37)    long  ->   a4         "CSE #44: aggressive"
+;  V59 cse2         [V59,T30] (  3,  38.36)    long  ->   a4         "CSE #48: moderate"
+;  V60 cse3         [V60,T43] (  3,  15.00)    long  ->   a3         "CSE #03: moderate"
+;  V61 cse4         [V61,T09] (  3,1927.73)    long  ->   a3         "CSE #20: aggressive"
+;  V62 cse5         [V62,T21] (  4, 650.92)    long  ->   a3         "CSE #39: moderate"
+;  V63 cse6         [V63,T25] (  5, 359.45)    long  ->   a4         "CSE #25: moderate"
+;  V64 cse7         [V64,T42] (  3,  15.01)    long  ->   a3         "CSE #10: moderate"
+;  V65 cse8         [V65,T28] (  3, 234.69)     ref  ->   a1         hoist "CSE #23: moderate"
+;  V66 rat0         [V66,T36] (  4,  16.10)   byref  ->   a2         "Strength reduced derived IV"
+;  V67 rat1         [V67,T37] (  4,  16.10)     int  ->   a3         "Trip count IV"
+;  V68 rat2         [V68,T38] (  4,  15.78)   byref  ->   a1         "Strength reduced derived IV"
+;  V69 rat3         [V69,T40] (  4,  15.78)     int  ->   a3         "Trip count IV"
+;  V70 rat4         [V70,T39] (  4,  15.78)   byref  ->   a0         "Strength reduced derived IV"
+;  V71 rat5         [V71,T41] (  4,  15.78)     int  ->   a2         "Trip count IV"
+;  V72 rat6         [V72,T52] (  3,   6   )     int  ->   a0         "ReplaceWithLclVar is creating a new local variable"
 ;
 ; Lcl frame size = 32
 Frame info. #outsz=0; #framesz=80; lcl=32
@@ -436,14 +435,25 @@ G_M44855_IG28:        ; bbWeight=109.94, gcrefRegs=0C00 {a0 a1}, byrefRegs=40200
             blt            t6, ra, G_M44855_IG13
 						;; size=60 bbWeight=109.94 PerfScore 2198.82
 G_M44855_IG29:        ; bbWeight=14.81, gcrefRegs=0C00 {a0 a1}, byrefRegs=40200 {s1 s2}, byref
+            mv             a3, a1, 
+            ; gcrRegs +[a3]
+            lw             a5, 0xD1FFAB1E(a3)
+            sext.w         a6, a5
+            sext.w         a7, a2
+            bgeu           a7, a6, G_M44855_IG67
+            add            a5, a3, a4
+            ; byrRegs +[a5]
+            lhu            a3, 0xD1FFAB1E(a5)
+            ; gcrRegs -[a3]
             add            a4, s4, a4
             lhu            a4, 0xD1FFAB1E(a4)
             slliw          ra, a3, 0
             slliw          t6, a4, 0
             bge            ra, t6, G_M44855_IG46
-						;; size=20 bbWeight=14.81 PerfScore 118.50
+						;; size=48 bbWeight=14.81 PerfScore 274.03
 G_M44855_IG30:        ; bbWeight=33.09, gcrefRegs=0400 {a0}, byrefRegs=40200 {s1 s2}, byref
             ; gcrRegs -[a1]
+            ; byrRegs -[a5]
             sext.w         a1, zero
             addi           a2, zero, 0xD1FFAB1E
 						;; size=8 bbWeight=33.09 PerfScore 33.09
@@ -644,10 +654,8 @@ G_M44855_IG49:        ; bbWeight=0.10, gcrefRegs=0C00 {a0 a1}, byrefRegs=C0200 {
             sext.w         a5, a4
             sext.w         a6, a3
             bgeu           a6, a5, G_M44855_IG67
-            slli           a4, a3, 32
-            srli           a4, a4, 32
-            slli           a4, a4, 1
-            add            a5, a1, a4
+            mv             a4, a3, 
+            sh1add.uw      a5, a4, a1
             ; byrRegs +[a5]
             lhu            a4, 0xD1FFAB1E(a5)
             or             a2, a4, a2
@@ -657,7 +665,7 @@ G_M44855_IG49:        ; bbWeight=0.10, gcrefRegs=0C00 {a0 a1}, byrefRegs=C0200 {
             addi           ra, zero, 0xD1FFAB1E
             blt            t6, ra, G_M44855_IG49
             j              G_M44855_IG11
-						;; size=64 bbWeight=0.10 PerfScore 1.90
+						;; size=56 bbWeight=0.10 PerfScore 1.80
 G_M44855_IG50:        ; bbWeight=0.10, gcrefRegs=0400 {a0}, byrefRegs=0200 {s1}, byref
             ; gcrRegs -[a1]
             ; byrRegs -[a5 s2-s3]
@@ -665,10 +673,8 @@ G_M44855_IG50:        ; bbWeight=0.10, gcrefRegs=0400 {a0}, byrefRegs=0200 {s1},
             sext.w         a4, a3
             sext.w         a5, a2
             bgeu           a5, a4, G_M44855_IG67
-            slli           a3, a2, 32
-            srli           a3, a3, 32
-            slli           a3, a3, 1
-            add            a4, a0, a3
+            mv             a3, a2, 
+            sh1add.uw      a4, a3, a0
             ; byrRegs +[a4]
             lhu            a3, 0xD1FFAB1E(a4)
             or             a1, a3, a1
@@ -678,7 +684,7 @@ G_M44855_IG50:        ; bbWeight=0.10, gcrefRegs=0400 {a0}, byrefRegs=0200 {s1},
             addi           ra, zero, 0xD1FFAB1E
             blt            t6, ra, G_M44855_IG50
             j              G_M44855_IG43
-						;; size=64 bbWeight=0.10 PerfScore 1.90
+						;; size=56 bbWeight=0.10 PerfScore 1.80
 G_M44855_IG51:        ; bbWeight=0, gcrefRegs=0000 {}, byrefRegs=0200 {s1}, byref
             ; gcrRegs -[a0]
             ; byrRegs -[a4]
@@ -1030,7 +1036,7 @@ RWD00  	dd	G_M44855_IG51 - G_M44855_IG02
        	dd	G_M44855_IG60 - G_M44855_IG02
 
 
-; Total bytes of code 2580, prolog size 56, PerfScore 57340.07, instruction count 636, allocated bytes for code 2580 (MethodHash=27e550c8) for method EMFloat:DivideInternalFPF(byref,byref,byref) (Tier1)
+; Total bytes of code 2592, prolog size 56, PerfScore 57495.40, instruction count 639, allocated bytes for code 2592 (MethodHash=27e550c8) for method EMFloat:DivideInternalFPF(byref,byref,byref) (Tier1)
 ; ============================================================
 
 Unwind Info:
@@ -1041,7 +1047,7 @@ Unwind Info:
   E bit             : 0
   X bit             : 0
   Vers              : 0
-  Function Length   : 645 (0x00285) Actual length = 2580 (0x000a14)
+  Function Length   : 648 (0x00288) Actual length = 2592 (0x000a20)
   ---- Epilog scopes ----
   ---- Scope 0
   Epilog Start Offset        : 3523193630 (0xd1ffab1e) Actual offset = 3523193630 (0xd1ffab1e) Offset from main function begin = 3523193630 (0xd1ffab1e)
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
|test.mch|1,067|<span style="color:green">377</span>|<span style="color:red">4</span>|<span style="color:blue">686</span>|<span style="color:green">-10,216</span>|<span style="color:red">+36</span>|

---

#### PerfScore improvements/regressions per collection

|Collection|Contexts with diffs|Improvements|Regressions|Same PerfScore|Improvements (PerfScore)|Regressions (PerfScore)|PerfScore Overall in FullOpts|
|---|--:|--:|--:|--:|--:|--:|--:|
|test.mch|1,067|<span style="color:green">345</span>|<span style="color:red">3</span>|<span style="color:blue">719</span>|<span style="color:green">-1.30%</span>|<span style="color:red">+0.35%</span>|<span style="color:green">-0.1731%</span>|

---

#### Context information

|Collection|Diffed contexts|MinOpts|FullOpts|Missed, base|Missed, diff|
|---|--:|--:|--:|--:|--:|
|test.mch|12,755|10,245|2,510|0 (0.00%)|0 (0.00%)|


---

#### jit-analyze output


</div></details>
