Diffs are based on <span style="color:#1460aa">12,602</span> contexts (<span style="color:#1460aa">10,235</span> MinOpts, <span style="color:#1460aa">2,367</span> FullOpts).


<details>
<summary>Overall (<span style="color:green">-16,192</span> bytes)</summary>
<div style="margin-left:1em">

|Collection|Base size (bytes)|Diff size (bytes)|PerfScore in Diffs
|---|--:|--:|--:|
|test.mch|6,885,380|<span style="color:green">-16,192</span>|<span style="color:green">-0.45%</span>|


</div></details>

<details>
<summary>MinOpts (<span style="color:green">-7,400</span> bytes)</summary>
<div style="margin-left:1em">

|Collection|Base size (bytes)|Diff size (bytes)|PerfScore in Diffs
|---|--:|--:|--:|
|test.mch|5,357,720|<span style="color:green">-7,400</span>|<span style="color:green">-0.31%</span>|


</div></details>

<details>
<summary>FullOpts (<span style="color:green">-8,792</span> bytes)</summary>
<div style="margin-left:1em">

|Collection|Base size (bytes)|Diff size (bytes)|PerfScore in Diffs
|---|--:|--:|--:|
|test.mch|1,527,660|<span style="color:green">-8,792</span>|<span style="color:green">-0.68%</span>|


</div></details>

<details>
<summary>Example diffs</summary>
<div style="margin-left:1em">


<details>
<summary>test.mch</summary>
<div style="margin-left:1em">


<details>
<summary><span style="color:green">-12</span> (<span style="color:green">-11.54%</span>) : 3952.dasm - System.Collections.Immutable.ImmutableArray`1+Enumerator[System.__Canon]:get_Current():System.__Canon:this (Tier1)</summary>
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
<summary><span style="color:green">-12</span> (<span style="color:green">-8.57%</span>) : 822.dasm - System.IO.StringReader:Peek():int:this (Tier1)</summary>
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
<summary><span style="color:green">-12</span> (<span style="color:green">-8.11%</span>) : 12177.dasm - System.Collections.Concurrent.ConcurrentDictionary`2[System.Reflection.Metadata.TypeDefinitionHandle,System.__Canon]:GetBucket(System.Collections.Concurrent.ConcurrentDictionary`2+Tables[System.Reflection.Metadata.TypeDefinitionHandle,System.__Canon],int):System.Collections.Concurrent.ConcurrentDictionary`2+Node[System.Reflection.Metadata.TypeDefinitionHandle,System.__Canon] (Tier1)</summary>
<div style="margin-left:1em">

```diff
@@ -48,14 +48,11 @@ G_M22943_IG02:        ; bbWeight=1, gcrefRegs=0800 {a1}, byrefRegs=0000 {}, byre
             sext.w         a3, a2
             sext.w         a4, a1
             bgeu           a4, a3, G_M22943_IG04
-            slli           a1, a1, 32
-            srli           a1, a1, 32
-            slli           a1, a1, 3
             fence          3, 3
-            add            a2, a0, a1
+            sh3add.uw      a2, a1, a0
             ; byrRegs +[a2]
             ld             a0, 0xD1FFAB1E(a2)
-						;; size=88 bbWeight=1 PerfScore 27.50
+						;; size=76 bbWeight=1 PerfScore 26.00
 G_M22943_IG03:        ; bbWeight=1, epilog, nogc, extend
             ld             ra, 8(sp)
             ld             fp, 0(sp)
@@ -73,7 +70,7 @@ G_M22943_IG04:        ; bbWeight=0, gcVars=0000000000000000 {}, gcrefRegs=0000 {
             ebreak
 						;; size=28 bbWeight=0 PerfScore 0.00
 
-; Total bytes of code 148, prolog size 16, PerfScore 44.00, instruction count 37, allocated bytes for code 148 (MethodHash=2df3a660) for method System.Collections.Concurrent.ConcurrentDictionary`2[System.Reflection.Metadata.TypeDefinitionHandle,System.__Canon]:GetBucket(System.Collections.Concurrent.ConcurrentDictionary`2+Tables[System.Reflection.Metadata.TypeDefinitionHandle,System.__Canon],int):System.Collections.Concurrent.ConcurrentDictionary`2+Node[System.Reflection.Metadata.TypeDefinitionHandle,System.__Canon] (Tier1)
+; Total bytes of code 136, prolog size 16, PerfScore 42.50, instruction count 34, allocated bytes for code 136 (MethodHash=2df3a660) for method System.Collections.Concurrent.ConcurrentDictionary`2[System.Reflection.Metadata.TypeDefinitionHandle,System.__Canon]:GetBucket(System.Collections.Concurrent.ConcurrentDictionary`2+Tables[System.Reflection.Metadata.TypeDefinitionHandle,System.__Canon],int):System.Collections.Concurrent.ConcurrentDictionary`2+Node[System.Reflection.Metadata.TypeDefinitionHandle,System.__Canon] (Tier1)
 ; ============================================================
 
 Unwind Info:
@@ -84,7 +81,7 @@ Unwind Info:
   E bit             : 0
   X bit             : 0
   Vers              : 0
-  Function Length   : 37 (0x00025) Actual length = 148 (0x000094)
+  Function Length   : 34 (0x00022) Actual length = 136 (0x000088)
   ---- Epilog scopes ----
   ---- Scope 0
   Epilog Start Offset        : 3523193630 (0xd1ffab1e) Actual offset = 3523193630 (0xd1ffab1e) Offset from main function begin = 3523193630 (0xd1ffab1e)
```

</div></details>

<details>
<summary><span style="color:red">+8</span> (<span style="color:red">+1.49%</span>) : 4983.dasm - System.Collections.Generic.ArraySortHelper`1[System.__Canon]:SwapIfGreater(System.Span`1[System.__Canon],System.Comparison`1[System.__Canon],int,int) (Instrumented Tier1)</summary>
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
@@ -131,13 +125,17 @@ G_M47099_IG05:        ; bbWeight=0.50, gcrefRegs=0000 {}, byrefRegs=0200 {s1}, b
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
+            sh3add         t3, t3, s3
             ; byrRegs +[t3]
-            add            t6, s1, s3
+            mv             t4, s2, 
+            sh3add.uw      t6, t4, s3
             ld             t4, 0xD1FFAB1E(t6)
             ; gcrRegs +[t4]
             lui            t2, 0xD1FFAB1E
@@ -150,7 +148,9 @@ G_M47099_IG05:        ; bbWeight=0.50, gcrefRegs=0000 {}, byrefRegs=0200 {s1}, b
             jalr           ra, 0xD1FFAB1E(t2)		// CORINFO_HELP_CHECKED_ASSIGN_REF
             ; gcrRegs -[t4]
             ; byrRegs -[t3 t6]
-            add            t3, s1, s3
+            slli           t3, s2, 32
+            srli           t3, t3, 32
+            sh3add         t3, t3, s3
             ; byrRegs +[t3]
             mv             t4, a0, 
             ; gcrRegs +[t4]
@@ -163,8 +163,8 @@ G_M47099_IG05:        ; bbWeight=0.50, gcrefRegs=0000 {}, byrefRegs=0200 {s1}, b
             slli           t2, t2, 10
             jalr           ra, 0xD1FFAB1E(t2)		// CORINFO_HELP_CHECKED_ASSIGN_REF
             ; gcrRegs -[a0 t4]
-            ; byrRegs -[s1 t3]
-						;; size=144 bbWeight=0.50 PerfScore 17.75
+            ; byrRegs -[s3 t3]
+						;; size=168 bbWeight=0.50 PerfScore 19.25
 G_M47099_IG06:        ; bbWeight=1, gcrefRegs=0000 {}, byrefRegs=0000 {}, byref
             lui            a0, 0xD1FFAB1E
             addiw          a0, a0, 0xD1FFAB1E
@@ -200,7 +200,7 @@ G_M47099_IG08:        ; bbWeight=0, gcVars=0000000000000000 {}, gcrefRegs=0000 {
             ebreak
 						;; size=28 bbWeight=0 PerfScore 0.00
 
-; Total bytes of code 536, prolog size 36, PerfScore 127.75, instruction count 120, allocated bytes for code 536 (MethodHash=50934804) for method System.Collections.Generic.ArraySortHelper`1[System.__Canon]:SwapIfGreater(System.Span`1[System.__Canon],System.Comparison`1[System.__Canon],int,int) (Instrumented Tier1)
+; Total bytes of code 544, prolog size 36, PerfScore 127.25, instruction count 122, allocated bytes for code 544 (MethodHash=50934804) for method System.Collections.Generic.ArraySortHelper`1[System.__Canon]:SwapIfGreater(System.Span`1[System.__Canon],System.Comparison`1[System.__Canon],int,int) (Instrumented Tier1)
 ; ============================================================
 
 Unwind Info:
@@ -211,7 +211,7 @@ Unwind Info:
   E bit             : 0
   X bit             : 0
   Vers              : 0
-  Function Length   : 134 (0x00086) Actual length = 536 (0x000218)
+  Function Length   : 136 (0x00088) Actual length = 544 (0x000220)
   ---- Epilog scopes ----
   ---- Scope 0
   Epilog Start Offset        : 3523193630 (0xd1ffab1e) Actual offset = 3523193630 (0xd1ffab1e) Offset from main function begin = 3523193630 (0xd1ffab1e)
```

</div></details>

<details>
<summary><span style="color:red">+4</span> (<span style="color:red">+0.50%</span>) : 338.dasm - System.SpanHelpers:IndexOfNullCharacter(ulong):int (Instrumented Tier1)</summary>
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
@@ -264,12 +265,11 @@ G_M54480_IG19:        ; bbWeight=0.06, epilog, nogc, extend
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
 						;; size=64 bbWeight=0.01 PerfScore 0.12
 
-; Total bytes of code 800, prolog size 32, PerfScore 76.26, instruction count 200, allocated bytes for code 800 (MethodHash=e0692b2f) for method System.SpanHelpers:IndexOfNullCharacter(ulong):int (Instrumented Tier1)
+; Total bytes of code 804, prolog size 32, PerfScore 76.19, instruction count 201, allocated bytes for code 804 (MethodHash=e0692b2f) for method System.SpanHelpers:IndexOfNullCharacter(ulong):int (Instrumented Tier1)
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
<summary><span style="color:red">+12</span> (<span style="color:red">+0.46%</span>) : 554.dasm - EMFloat:DivideInternalFPF(byref,byref,byref) (Tier1)</summary>
<div style="margin-left:1em">

```diff
@@ -9,11 +9,11 @@
 ; 9 inlinees with PGO data; 2 single block inlinees; 0 inlinees without PGO data
 ; Final local variable assignments
 ;
-;  V00 arg0         [V00,T45] ( 12,  11   )   byref  ->   s3         single-def
+;  V00 arg0         [V00,T44] ( 12,  11   )   byref  ->   s3         single-def
 ;  V01 arg1         [V01,T26] ( 14, 279.43)   byref  ->   s2         single-def
 ;  V02 arg2         [V02,T24] ( 31, 401.74)   byref  ->   s1         single-def
-;  V03 loc0         [V03,T34] (  6,  26.01)     int  ->   a1        
-;  V04 loc1         [V04,T16] ( 12,1179.76)     int  ->   a2        
+;  V03 loc0         [V03,T33] (  6,  26.01)     int  ->   a1        
+;  V04 loc1         [V04,T16] ( 13,1194.77)     int  ->   a2        
 ;  V05 loc2         [V05,T00] ( 15,4568.26)  ushort  ->   a1         ld-addr-op
 ;  V06 loc3         [V06,T11] (  8,1732.34)    long  ->   s4         class-hnd exact single-def <ushort[]>
 ;* V07 loc4         [V07    ] (  0,   0   )  struct (16) zero-ref    ld-addr-op <EMFloat+InternalFPF>
@@ -23,14 +23,14 @@
 ;* V11 tmp1         [V11    ] (  0,   0   )    long  ->  zero-ref    class-hnd exact "NewArr temp" <ushort[]>
 ;  V12 tmp2         [V12,T19] (  3, 769.48)   byref  ->   a1         "dup spill"
 ;* V13 tmp3         [V13    ] (  0,   0   )     ref  ->  zero-ref    class-hnd exact "NewArr temp" <ushort[]>
-;  V14 tmp4         [V14,T35] (  6,  26.00)     int  ->   a1         "Inline stloc first use temp"
-;  V15 tmp5         [V15,T36] (  2,  20.00)     int  ->   a2         "Strict ordering of exceptions for Array store"
-;  V16 tmp6         [V16,T48] (  4,  12.03)     int  ->   a1         "Inline stloc first use temp"
-;* V17 tmp7         [V17,T58] (  0,   0   )     int  ->  zero-ref    "Inline stloc first use temp"
-;* V18 tmp8         [V18,T55] (  0,   0   )     ref  ->  zero-ref    class-hnd single-def "Inlining Arg" <ushort[]>
-;  V19 tmp9         [V19,T46] (  6,  12.03)     int  ->   a2         "Inline stloc first use temp"
-;  V20 tmp10        [V20,T56] (  6,   1.50)     int  ->   a3         "Inline stloc first use temp"
-;  V21 tmp11        [V21,T49] (  6,   8.34)     ref  ->   a1         class-hnd single-def "Inlining Arg" <ushort[]>
+;  V14 tmp4         [V14,T34] (  6,  26.00)     int  ->   a1         "Inline stloc first use temp"
+;  V15 tmp5         [V15,T35] (  2,  20.00)     int  ->   a2         "Strict ordering of exceptions for Array store"
+;  V16 tmp6         [V16,T47] (  4,  12.03)     int  ->   a1         "Inline stloc first use temp"
+;* V17 tmp7         [V17,T57] (  0,   0   )     int  ->  zero-ref    "Inline stloc first use temp"
+;* V18 tmp8         [V18,T54] (  0,   0   )     ref  ->  zero-ref    class-hnd single-def "Inlining Arg" <ushort[]>
+;  V19 tmp9         [V19,T45] (  6,  12.03)     int  ->   a2         "Inline stloc first use temp"
+;  V20 tmp10        [V20,T55] (  6,   1.50)     int  ->   a3         "Inline stloc first use temp"
+;  V21 tmp11        [V21,T48] (  6,   8.34)     ref  ->   a1         class-hnd single-def "Inlining Arg" <ushort[]>
 ;  V22 tmp12        [V22,T06] (  5,2677.63)     int  ->   a2         "Inline stloc first use temp"
 ;* V23 tmp13        [V23,T27] (  0,   0   )     ref  ->  zero-ref    class-hnd "Inlining Arg" <ushort[]>
 ;  V24 tmp14        [V24,T03] (  7,3283.79)  ushort  ->   a4         "Inline stloc first use temp"
@@ -46,43 +46,42 @@
 ;  V34 tmp24        [V34,T01] (  9,3346.77)     ref  ->   a2         class-hnd "Inlining Arg" <ushort[]>
 ;  V35 tmp25        [V35,T02] ( 14,3283.79)  ushort  ->   a5         "Inline stloc first use temp"
 ;  V36 tmp26        [V36,T13] (  4,1274.69)     int  ->   a6         "Inline stloc first use temp"
-;  V37 tmp27        [V37,T51] (  3,   6.00)   byref  ->   a1         single-def "dup spill"
-;  V38 tmp28        [V38,T54] (  7,   2.00)     int  ->   a1         "Inline stloc first use temp"
-;  V39 tmp29        [V39,T59] (  3,   0   )   byref  ->   a0         single-def "dup spill"
-;  V40 tmp30        [V40,T60] (  3,   0   )     ref  ->   s1         class-hnd exact single-def "NewObj constructor temp" <<unknown class>>
-;  V41 tmp31        [V41,T47] (  6,  12.03)     int  ->   a1         "Inline stloc first use temp"
-;  V42 tmp32        [V42,T57] (  6,   1.50)     int  ->   a2         "Inline stloc first use temp"
-;  V43 tmp33        [V43,T50] (  6,   8.34)     ref  ->   a0         class-hnd single-def "Inlining Arg" <ushort[]>
+;  V37 tmp27        [V37,T50] (  3,   6.00)   byref  ->   a1         single-def "dup spill"
+;  V38 tmp28        [V38,T53] (  7,   2.00)     int  ->   a1         "Inline stloc first use temp"
+;  V39 tmp29        [V39,T58] (  3,   0   )   byref  ->   a0         single-def "dup spill"
+;  V40 tmp30        [V40,T59] (  3,   0   )     ref  ->   s1         class-hnd exact single-def "NewObj constructor temp" <<unknown class>>
+;  V41 tmp31        [V41,T46] (  6,  12.03)     int  ->   a1         "Inline stloc first use temp"
+;  V42 tmp32        [V42,T56] (  6,   1.50)     int  ->   a2         "Inline stloc first use temp"
+;  V43 tmp33        [V43,T49] (  6,   8.34)     ref  ->   a0         class-hnd single-def "Inlining Arg" <ushort[]>
 ;  V44 tmp34        [V44    ] (  3,   3   )  struct (24) [fp-0x18]   do-not-enreg[XS] must-init addr-exposed "stack allocated array temp" <ushort[]>
 ;  V45 tmp35        [V45,T12] (  5,1281.69)     ref  ->   a0         single-def "field V07.mantissa (fldOffset=0x0)" P-INDEP
 ;* V46 tmp36        [V46    ] (  0,   0   )   short  ->  zero-ref    "field V07.exp (fldOffset=0x8)" P-INDEP
 ;* V47 tmp37        [V47    ] (  0,   0   )   ubyte  ->  zero-ref    "field V07.type (fldOffset=0xa)" P-INDEP
 ;* V48 tmp38        [V48    ] (  0,   0   )   ubyte  ->  zero-ref    "field V07.sign (fldOffset=0xb)" P-INDEP
-;  V49 tmp39        [V49,T33] (  3,  30.00)     ref  ->   a2         "arr expr"
+;  V49 tmp39        [V49,T32] (  3,  30.00)     ref  ->   a2         "arr expr"
 ;  V50 tmp40        [V50,T31] (  3,  30.02)     ref  ->   a2         "arr expr"
 ;  V51 tmp41        [V51,T18] (  3, 775.48)     ref  ->   a1         "arr expr"
 ;  V52 tmp42        [V52,T20] (  3, 661.34)     ref  ->   a3         "arr expr"
-;* V53 tmp43        [V53,T32] (  0,   0   )     ref  ->  zero-ref    "arr expr"
+;  V53 tmp43        [V53,T29] (  3,  90.04)     ref  ->   a3         "arr expr"
 ;  V54 tmp44        [V54,T17] (  3, 979.27)     ref  ->   a6         "arr expr"
-;  V55 tmp45        [V55,T52] (  3,   6.00)     ref  ->   a1         single-def "arr expr"
-;  V56 tmp46        [V56,T61] (  2,   0   )     ref  ->   a1         single-def "argument with side effect"
-;  V57 cse0         [V57,T28] (  3, 235.45)     int  ->   a3         "CSE #29: moderate"
-;  V58 cse1         [V58,T08] (  3,1912.03)    long  ->   a3         "CSE #15: aggressive"
-;  V59 cse2         [V59,T10] (  3,1873.98)    long  ->   a4         "CSE #44: aggressive"
-;  V60 cse3         [V60,T30] (  3,  38.05)    long  ->   a4         "CSE #48: moderate"
-;  V61 cse4         [V61,T44] (  3,  15.00)    long  ->   a3         "CSE #03: moderate"
-;  V62 cse5         [V62,T09] (  3,1912.03)    long  ->   a3         "CSE #20: aggressive"
-;  V63 cse6         [V63,T21] (  4, 652.85)    long  ->   a3         "CSE #39: moderate"
-;  V64 cse7         [V64,T25] (  4, 345.68)    long  ->   a4         "CSE #25: moderate"
-;  V65 cse8         [V65,T43] (  3,  15.01)    long  ->   a3         "CSE #10: moderate"
-;  V66 cse9         [V66,T29] (  2, 220.44)     ref  ->   a1         hoist "CSE #23: moderate"
-;  V67 rat0         [V67,T37] (  4,  16.05)   byref  ->   a2         "Strength reduced derived IV"
-;  V68 rat1         [V68,T38] (  4,  16.05)     int  ->   a3         "Trip count IV"
-;  V69 rat2         [V69,T39] (  4,  15.73)   byref  ->   a1         "Strength reduced derived IV"
-;  V70 rat3         [V70,T41] (  4,  15.73)     int  ->   a3         "Trip count IV"
-;  V71 rat4         [V71,T40] (  4,  15.73)   byref  ->   a0         "Strength reduced derived IV"
-;  V72 rat5         [V72,T42] (  4,  15.73)     int  ->   a2         "Trip count IV"
-;  V73 rat6         [V73,T53] (  3,   6   )     int  ->   a0         "ReplaceWithLclVar is creating a new local variable"
+;  V55 tmp45        [V55,T51] (  3,   6.00)     ref  ->   a1         single-def "arr expr"
+;  V56 tmp46        [V56,T60] (  2,   0   )     ref  ->   a1         single-def "argument with side effect"
+;  V57 cse0         [V57,T08] (  3,1912.03)    long  ->   a3         "CSE #15: aggressive"
+;  V58 cse1         [V58,T10] (  3,1873.98)    long  ->   a4         "CSE #44: aggressive"
+;  V59 cse2         [V59,T30] (  3,  38.05)    long  ->   a4         "CSE #48: moderate"
+;  V60 cse3         [V60,T43] (  3,  15.00)    long  ->   a3         "CSE #03: moderate"
+;  V61 cse4         [V61,T09] (  3,1912.03)    long  ->   a3         "CSE #20: aggressive"
+;  V62 cse5         [V62,T21] (  4, 652.85)    long  ->   a3         "CSE #39: moderate"
+;  V63 cse6         [V63,T25] (  5, 360.68)    long  ->   a4         "CSE #25: moderate"
+;  V64 cse7         [V64,T42] (  3,  15.01)    long  ->   a3         "CSE #10: moderate"
+;  V65 cse8         [V65,T28] (  3, 235.45)     ref  ->   a1         hoist "CSE #23: moderate"
+;  V66 rat0         [V66,T36] (  4,  16.05)   byref  ->   a2         "Strength reduced derived IV"
+;  V67 rat1         [V67,T37] (  4,  16.05)     int  ->   a3         "Trip count IV"
+;  V68 rat2         [V68,T38] (  4,  15.73)   byref  ->   a1         "Strength reduced derived IV"
+;  V69 rat3         [V69,T40] (  4,  15.73)     int  ->   a3         "Trip count IV"
+;  V70 rat4         [V70,T39] (  4,  15.73)   byref  ->   a0         "Strength reduced derived IV"
+;  V71 rat5         [V71,T41] (  4,  15.73)     int  ->   a2         "Trip count IV"
+;  V72 rat6         [V72,T52] (  3,   6   )     int  ->   a0         "ReplaceWithLclVar is creating a new local variable"
 ;
 ; Lcl frame size = 32
 Frame info. #outsz=0; #framesz=80; lcl=32
@@ -436,14 +435,25 @@ G_M44855_IG28:        ; bbWeight=110.22, gcrefRegs=0C00 {a0 a1}, byrefRegs=40200
             blt            t6, ra, G_M44855_IG13
 						;; size=60 bbWeight=110.22 PerfScore 2204.47
 G_M44855_IG29:        ; bbWeight=15.01, gcrefRegs=0C00 {a0 a1}, byrefRegs=40200 {s1 s2}, byref
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
-						;; size=20 bbWeight=15.01 PerfScore 120.05
+						;; size=48 bbWeight=15.01 PerfScore 277.61
 G_M44855_IG30:        ; bbWeight=33.03, gcrefRegs=0400 {a0}, byrefRegs=40200 {s1 s2}, byref
             ; gcrRegs -[a1]
+            ; byrRegs -[a5]
             sext.w         a1, zero
             addi           a2, zero, 0xD1FFAB1E
 						;; size=8 bbWeight=33.03 PerfScore 33.03
@@ -643,10 +653,8 @@ G_M44855_IG49:        ; bbWeight=0.10, gcrefRegs=0400 {a0}, byrefRegs=0200 {s1},
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
@@ -656,7 +664,7 @@ G_M44855_IG49:        ; bbWeight=0.10, gcrefRegs=0400 {a0}, byrefRegs=0200 {s1},
             addi           ra, zero, 0xD1FFAB1E
             blt            t6, ra, G_M44855_IG49
             j              G_M44855_IG43
-						;; size=64 bbWeight=0.10 PerfScore 1.90
+						;; size=56 bbWeight=0.10 PerfScore 1.80
 G_M44855_IG50:        ; bbWeight=0.10, gcrefRegs=0C00 {a0 a1}, byrefRegs=C0200 {s1 s2 s3}, byref
             ; gcrRegs +[a1]
             ; byrRegs -[a4] +[s2-s3]
@@ -664,10 +672,8 @@ G_M44855_IG50:        ; bbWeight=0.10, gcrefRegs=0C00 {a0 a1}, byrefRegs=C0200 {
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
@@ -677,7 +683,7 @@ G_M44855_IG50:        ; bbWeight=0.10, gcrefRegs=0C00 {a0 a1}, byrefRegs=C0200 {
             addi           ra, zero, 0xD1FFAB1E
             blt            t6, ra, G_M44855_IG50
             j              G_M44855_IG11
-						;; size=64 bbWeight=0.10 PerfScore 1.90
+						;; size=56 bbWeight=0.10 PerfScore 1.80
 G_M44855_IG51:        ; bbWeight=0, gcrefRegs=0000 {}, byrefRegs=0200 {s1}, byref
             ; gcrRegs -[a0-a1]
             ; byrRegs -[a5 s2-s3]
@@ -1031,7 +1037,7 @@ RWD00  	dd	G_M44855_IG51 - G_M44855_IG02
        	dd	G_M44855_IG60 - G_M44855_IG02
 
 
-; Total bytes of code 2588, prolog size 56, PerfScore 57007.20, instruction count 638, allocated bytes for code 2588 (MethodHash=27e550c8) for method EMFloat:DivideInternalFPF(byref,byref,byref) (Tier1)
+; Total bytes of code 2600, prolog size 56, PerfScore 57164.56, instruction count 641, allocated bytes for code 2600 (MethodHash=27e550c8) for method EMFloat:DivideInternalFPF(byref,byref,byref) (Tier1)
 ; ============================================================
 
 Unwind Info:
@@ -1042,7 +1048,7 @@ Unwind Info:
   E bit             : 0
   X bit             : 0
   Vers              : 0
-  Function Length   : 647 (0x00287) Actual length = 2588 (0x000a1c)
+  Function Length   : 650 (0x0028a) Actual length = 2600 (0x000a28)
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
|test.mch|1,333|<span style="color:green">736</span>|<span style="color:red">4</span>|<span style="color:blue">593</span>|<span style="color:green">-16,220</span>|<span style="color:red">+28</span>|

---

#### PerfScore improvements/regressions per collection

|Collection|Contexts with diffs|Improvements|Regressions|Same PerfScore|Improvements (PerfScore)|Regressions (PerfScore)|PerfScore Overall in FullOpts|
|---|--:|--:|--:|--:|--:|--:|--:|
|test.mch|1,333|<span style="color:green">703</span>|<span style="color:red">3</span>|<span style="color:blue">627</span>|<span style="color:green">-0.85%</span>|<span style="color:red">+0.35%</span>|<span style="color:green">-0.1472%</span>|

---

#### Context information

|Collection|Diffed contexts|MinOpts|FullOpts|Missed, base|Missed, diff|
|---|--:|--:|--:|--:|--:|
|test.mch|12,602|10,235|2,367|0 (0.00%)|0 (0.00%)|


---

#### jit-analyze output


</div></details>

