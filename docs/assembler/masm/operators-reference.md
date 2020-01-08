---
title: Referenz für MASM-Operatoren
ms.date: 12/17/2019
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), operators reference
- operators [MASM]
ms.assetid: c069cab7-d6b0-4f82-a6ce-0ca3fc7e6428
ms.openlocfilehash: c0059ab1b0204b79e040d18bd5aa88145775ebcd
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318760"
---
# <a name="masm-operators-reference"></a>Referenz für MASM-Operatoren

## <a name="arithmetic"></a>Arithmetisch

||||
|-|-|-|
|[* (multiplizieren)](operator-multiply.md)|[+ (hinzufügen)](operator-add.md)|[-(subtrahieren oder negieren)](operator-subtract-2.md)|
|[. Flächen](operator-dot.md)|[/(dividieren)](operator-subtract-1.md)|[&#91;&#93;Sin](operator-brackets.md)|
|[MOD (Rest)](operator-mod.md)|||

## <a name="control-flow"></a>Ablaufsteuerung

||||
|-|-|-|
|[\! (logische Laufzeit nicht)](operator-logical-not-masm-run-time.md)|[\!= (Laufzeit nicht gleich)](operator-not-equal-masm.md)|[&#124;&#124;(logischer Lauf Zeit Modul oder)](operator-logical-or.md)|
|[& & (logisches und-Lauf Zeit Modul)](operator-logical-and-masm-run-time.md)|[< (Laufzeit kleiner als)](operator-less-than-masm-run-time.md)|[\<= (Laufzeit ist kleiner oder gleich)](operator-less-or-equal-masm-run-time.md)|
|[= = (Runtime gleich)](operator-equal-masm-run-time.md)|[> (Laufzeit größer als)](operator-greater-than-masm-run-time.md)|[> = (Laufzeit größer oder gleich)](operator-greater-or-equal-masm-run-time.md)|
|[& (Bitweises and-Lauf Zeit Modul)](operator-bitwise-and.md)|||
|[Erledigen? (Lauf Zeit Test ausführen)](operator-carry-q.md)|[Läufen? (Lauf Zeit Überlauf Test)](operator-overflow-q.md)|[Parity? (Lauf Zeit Paritäts Test)](operator-parity-q.md)|
|[Gebärden? (Lauf Zeit Signatur-Test)](operator-sign-q.md)|[Zins? (Lauf Zeit Zero-Test)](operator-zero-q.md)||

## <a name="logical-and-shift"></a>Logisches und Shift

||||
|-|-|-|
|[Und (Bitweises and)](operator-and.md)|[Not (Bitweises NOT)](operator-not.md)|[Or (Bitweises OR)](operator-or.md)|
|[SHL (UMSCHALT Bits nach links)](operator-shl.md)|[SHR (Shift Bits right)](operator-shr.md)|[XOR (Bitweises exklusives OR)](operator-xor.md)|

## <a name="macro"></a>Makro

||||
|-|-|-|
|[\! (Zeichenliteral)](operator-logical-not-masm.md)|[% (als Text behandeln)](operator-percent.md)||
|[;; (als Kommentar behandeln)](operator-semicolons.md)|[&lt; &gt; (als ein Literalformat behandeln)](operator-literal.md)|[& & (Parameterwert ersetzen)](operator-logical-and-masm.md)|

## <a name="miscellaneous"></a>Verschiedenes

||||
|-|-|-|
|["" (als Zeichenfolge behandeln)](operator-single-quote.md)|["" (als Zeichenfolge behandeln)](operator-double-quote.md)||
|: (Definition der lokalen Bezeichnung)|:: (Register Segment und Offset)|:: (Definition der globalen Bezeichnung)|
|[; (als Kommentar behandeln)](operator-semicolon.md)|[DUP (Wiederholungs Deklaration)](operator-dup.md)||

## <a name="record"></a>Aufnahme

|||
|-|-|
|[Mask (Datensatz-oder Feld-Bitmaske)](operator-mask.md)|[Breite (Datensatz-oder Feldbreite erhalten)](operator-width.md)|

## <a name="relational"></a>Relational

||||
|-|-|-|
|[EQ (gleich)](operator-eq.md)|[GE (größer oder gleich)](operator-ge.md)|[GT (größer als)](operator-gt.md)|
|[Le (kleiner oder gleich)](operator-le.md)|[LT (kleiner als)](operator-lt.md)|[NE (ungleich)](operator-ne.md)|

## <a name="segment"></a>Segment

|||
|-|-|
|[: (Segment Überschreibung)](operator-colon.md)|:: (Register Segment und Offset)|
|[IMAGEREL (Bild relativer Offset)](operator-imagerel.md)|[Lroffset (Offset des Lade Moduls)](operator-lroffset.md)|
|[Offset (relativer Segment Vergleich)](operator-offset.md)|[SECTIONREL (Abschnitts relativer Offset)](operator-sectionrel.md)|
|[ABG (Segment erhalten)](operator-seg.md)||

## <a name="type"></a>Typ

||||
|-|-|-|
|[Hoch (hohe 8 Bits der niedrigsten 16 Bits)](operator-high.md)|[HIGH32 (hohe 32 Bits von 64 Bits)](operator-high32.md)|[HighWord (hohe 16 Bits der niedrigsten 32 Bits)](operator-highword.md)|
|[LENGTH (Anzahl von Elementen im Array)](operator-length.md)|[Lengthof (Anzahl von Elementen im Array)](operator-lengthof.md)|[Niedrig (niedrige 8 Bits)](operator-low.md)|
|[LOW32 (niedrige 32 Bits)](operator-low32.md)|[Lowword (niedrige 16 Bits)](operator-lowword.md)|[OPATTR (Get-Argumenttyp Info)](operator-opattr.md)|
|[PTR (Zeiger auf oder als Typ)](operator-ptr.md)|[Short (Bezeichnung für kurze Bezeichnung markieren)](operator-short.md)|[Größe (Größe des Typs oder der Variablen)](operator-size.md)|
|[Sizeof (Größe des Typs oder der Variablen)](operator-sizeof.md)|[This (Aktueller Speicherort)](operator-this.md)|[Type (Ausdruck ' Ausdruck ' eingeben)](operator-type.md)|
|[. Type (Argument-Typinformationen Get)](operator-dot-type.md)|||

## <a name="see-also"></a>Siehe auch

[Microsoft Macro Assembler-Referenz](microsoft-macro-assembler-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
