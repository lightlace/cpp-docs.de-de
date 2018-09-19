---
title: MASM-Operatoren – Referenz | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), operators reference
- operators [MASM]
ms.assetid: c069cab7-d6b0-4f82-a6ce-0ca3fc7e6428
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4708af3c0fa272a1ca803f549ce8953caccaa27
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688175"
---
# <a name="masm-operators-reference"></a>MASM-Operatoren – Referenz

## <a name="arithmetic"></a>Arithmetisch

||||
|-|-|-|
|[* (Multiplikation)](operator-multiply.md)|[+ (Addition)](operator-add.md)|[-(Subtraktion oder Negation)](operator-subtract-2.md)|
|[. (Feld)](operator-dot.md)|[/ (Division)](operator-subtract-1.md)|[&#91;&#93;(Index)](operator-brackets.md)|
|[Modulo (Rest)](operator-mod.md)|||

## <a name="control-flow"></a>Ablaufsteuerung

||||
|-|-|-|
|[! (logisches Not für Common Language Runtime)](operator-logical-not-masm-run-time.md)|[! = (ungleich-Laufzeit)](operator-not-equal-masm.md)|[&#124;&#124;(Common Language Runtime logische oder)](operator-logical-or.md)|
|[& & (logisches Runtime und)](operator-logical-and-masm-run-time.md)|[< (Common Language Runtime kleiner als)](operator-less-than-masm-run-time.md)|[\<= (Runtime kleiner als oder gleich)](operator-less-or-equal-masm-run-time.md)|
|[== (gleich-Laufzeit)](operator-equal-masm-run-time.md)|[> (größer als-Laufzeit)](operator-greater-than-masm-run-time.md)|[> = (Runtime größer oder gleich)](operator-greater-or-equal-masm-run-time.md)|
|[& (Common Language Runtime bitweises und)](operator-bitwise-and.md)|||
|[CARRY? (Common Language Runtime Carry-Test)](operator-carry-q.md)|[OVERFLOW? (Common Language Runtime-Überlauf-Test)](operator-overflow-q.md)|[PARITY? (Common Language Runtime Parität Test)](operator-parity-q.md)|
|[MELDEN SIE SICH? (Common Language Runtime-anmelden-Test)](operator-sign-q.md)|[0 (NULL)? (Common Language Runtime 0 (null) Test)](operator-zero-q.md)||

## <a name="logical-and-shift"></a>Logischer and -Shift

||||
|-|-|-|
|[UND (bitweises und)](operator-and.md)|[KEINE (bitweises Not)](operator-not.md)|[OR (bitweises oder)](operator-or.md)|
|[SHL (UMSCHALT Bits nach links)](operator-shl.md)|[SHR (Rechte UMSCHALTTASTE, Bits)](operator-shr.md)|[XOR (Bitweises exklusives oder)](operator-xor.md)|

## <a name="macro"></a>Makro

||||
|-|-|-|
|[! (Zeichenliteral)](operator-logical-not-masm.md)|[% (Hana als Text)](operator-percent.md)||
|[;; (als Kommentar behandelt)](operator-semicolons.md)|[&lt; &gt; (ein Literal identisch behandelt)](operator-literal.md)|[& & (Parameterwert ersetzen)](operator-logical-and-masm.md)|

## <a name="miscellaneous"></a>Verschiedenes

||||
|-|-|-|
|["" (als Zeichenfolge behandeln)](operator-single-quote.md)|["" (als Zeichenfolge behandeln)](operator-double-quote.md)||
|: (lokale Bezeichnung Definition)|:: (Segmente und Offsets registrieren)|:: (Bezeichnung der globalen Definition)|
|[; (als Kommentar behandelt)](operator-semicolon.md)|[DUP (Wiederholen Sie diesen Schritt Deklaration)](operator-dup.md)||

## <a name="record"></a>Datensatz

|||
|-|-|
|[MASKE (get Datensatz- oder Feldknoten Bitmaske)](operator-mask.md)|[Breite (Datensatz- oder Feldknoten Breite abrufen)](operator-width.md)|

## <a name="relational"></a>Relational

||||
|-|-|-|
|[EQ (gleich)](operator-eq.md)|[GE (größer oder gleich)](operator-ge.md)|[GT (größer als)](operator-gt.md)|
|[LE (kleiner oder gleich)](operator-le.md)|[LT (kleiner als)](operator-lt.md)|[NE (ungleich)](operator-ne.md)|

## <a name="segment"></a>Segment

|||
|-|-|
|[: (segment außer Kraft setzen)](operator-colon.md)|:: (Segmente und Offsets registrieren)|
|[IMAGEREL (relative Bildoffset)](operator-imagerel.md)|[LROFFSET (Ladeprogramm aufgelöst Offset)](operator-lroffset.md)|
|[OFFSET (Segment relativen Offset)](operator-offset.md)|[SECTIONREL (Abschnitt relativen Offset)](operator-sectionrel.md)|
|[SEG (Get-Segment)](operator-seg.md)||

## <a name="type"></a>Typ

||||
|-|-|-|
|[Hoch (hohe 8 Bit der niedrigsten 16 Bits)](operator-high.md)|[HIGH32 (oberen 32 Bits des 64-Bit)](operator-high32.md)|[HIGHWORD (oberen 16 Bits der niedrigsten 32-Bit)](operator-highword.md)|
|[Länge (Anzahl der Elemente im Array)](operator-length.md)|[LENGTHOF (Anzahl der Elemente im Array)](operator-lengthof.md)|[Niedrig (unteren 8 Bits)](operator-low.md)|
|[LOW32 (niedrige 32 Bits)](operator-low32.md)|[LOWWORD (unteren 16 Bits)](operator-lowword.md)|[OPATTR (Get-Argument-Typinformationen)](operator-opattr.md)|
|[PTR (Zeiger oder als Typ)](operator-ptr.md)|[SHORT (kurz Bezeichnungstyp markieren)](operator-short.md)|[Größe (Größe des Typs oder einer Variablen)](operator-size.md)|
|["Sizeof" (Größe des Typs oder einer Variablen)](operator-sizeof.md)|[Diese (Position)](operator-this.md)|[Typ (Get-Ausdruck-Typ)](operator-type.md)|
|[. Typ (Get-Argument-Typinformationen)](operator-dot-type.md)|||

## <a name="see-also"></a>Siehe auch

[Referenz zum Microsoft-Makroassembler](microsoft-macro-assembler-reference.md)<br/>