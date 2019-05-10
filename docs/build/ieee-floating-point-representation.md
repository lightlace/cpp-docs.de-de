---
title: IEEE-Gleitkommadarstellung
ms.date: 05/06/2019
helpviewer_keywords:
- float keyword
- real*8 value
- floating-point numbers, IEEE representation
- double data type, floating-point representation
- IEEE floating point representation
- real*10 value
- long double
- real*4 value
ms.assetid: 537833e8-fe05-49fc-8169-55fd0314b195
ms.openlocfilehash: 130a79ae6846df27ffabfd6cb6649e0a0de03e4b
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220624"
---
# <a name="ieee-floating-point-representation"></a>IEEE-Gleitkommadarstellung

Microsoft C++ (MSVC) ist konsistent mit den numerischen IEEE-Standards. Der IEEE-754-Standard beschreibt Gleitkomma-Formate, eine Methode zur Darstellung der reellen Zahlen in der Hardware. Es gibt mindestens fünf interne Formate für Gleitkommazahlen, die in der Hardware, die das Ziel des MSVC-Compilers darstellbar sind, aber der Compiler verwendet nur zwei davon. Die *mit einfacher Genauigkeit* (4-Byte) und *mit doppelter Genauigkeit* (8 Byte)-Formate in MSVC verwendet werden. Mit einfacher Genauigkeit ist deklariert, mit dem Schlüsselwort **"float"**. Gleitkommazahl mit doppelter Genauigkeit ist deklariert, mit dem Schlüsselwort **doppelte**. Der IEEE-Standard gibt auch an *Hälfte mit einfacher Genauigkeit* (2-Byte) und *Quadrupel mit einfacher Genauigkeit* Formate (16-Byte), sowie einen *erweitert – mit doppelter Genauigkeit* (10 Byte) Format, das einige C- und C++-Compiler als implementieren die **long double** -Datentyp. In der MSVC-Compiler die **long double** -Datentyp wird als gesonderter Typ behandelt, aber der Storage-Typ zugeordnet ist, um **doppelte**. Vorhanden ist, jedoch systeminterne und Assembly-sprachunterstützung für Berechnungen mit den anderen Formaten, einschließlich des erweiterten-mit doppelter Genauigkeit (10 Byte)-Formats, wobei von Hardware unterstützt.

Die Werte werden wie folgt gespeichert:

|Wert|Als gespeichert|
|-----------|---------------|
|mit einfacher Genauigkeit|Vorzeichenbit, 8-Bit-Exponenten, 23-Bit-Signifikanden|
|double-precision|Melden Sie Bit, 11-Bit-Exponenten und 52-Bit-Signifikanden|
|double-extended-precision|Vorzeichenbit, 15-Bit-Exponenten, 64-Bit-Signifikanden|

In Formaten mit einfacher Genauigkeit und mit doppelter Genauigkeit, besteht eine führende 1 in der Bruchteil wird aufgerufen, die *Signifikanden* (und mitunter als die *Mantisse*), d. h. nicht gespeichert Arbeitsspeicher, sodass Signifikanden eigentlich 24 bzw. 53 Bits sind, obwohl nur 23 oder 52 Bits gespeichert werden. Das Format des erweiterten-mit doppelter Genauigkeit wird tatsächlich Bits gespeichert.

Die Exponenten werden mit der Hälfte ihres möglichen Werts gewichtet. Dies bedeutet, dass Sie diese Verschiebung von der gespeicherten Exponent zum Abrufen der tatsächlichen Exponent subtrahieren. Wenn der gespeicherte Exponent kleiner als die Verschiebung ist, ist es tatsächlich einen negativen Exponenten.

Die Exponenten beziehen sich wie folgt:

|Exponent|Gewichtet mit|
|--------------|---------------|
|8-Bit-(Genauigkeit)|127|
|11-Bit-(Genauigkeit)|1023|
|15-Bit-(extended-Genauigkeit)|16383|

Diese Exponenten sind nicht Zehnerpotenzen. Es handelt sich um Potenzen von 2. D. h. reichen gespeicherte 8-Bit-Exponenten-127 bis 127, gespeichert als 0 und 254 von. Der Wert 2<sup>127</sup> entspricht ungefähr 10<sup>38</sup>, d.h., dass der tatsächliche Grenzwert von mit einfacher Genauigkeit.

Die Mantisse wird als Binärbruch des Formulars gespeichert... 1.xxx.... Dieser Anteil hat es sich um einen Wert größer als oder gleich 1 und kleiner als 2. Beachten Sie, dass die reellen Zahlen, die immer in gespeichert werden *normalisierte Form*; d. h. die Mantisse wird nach links verschoben, dass das höchstwertige Bit der Mantisse immer 1 ist. Da dieses Bit immer 1 ist, wird davon ausgegangen (aber nicht gespeichert) in den Formaten mit einfacher Genauigkeit und mit doppelter Genauigkeit. Der binärpunkt (nicht dezimal) wird davon ausgegangen, dass rechts von der führenden 1 sein.

Das Format ist, für die verschiedenen Größen wie folgt:

|Format|byte 1|2-Byte|Byte-3|byte 4|...|Byte-n|
|------------|------------|------------|------------|------------|---------|------------|
|mit einfacher Genauigkeit| `SXXXXXXX`|`XMMMMMMM`|`MMMMMMMM`|`MMMMMMMM`|||
|double-precision|`SXXXXXXX`|`XXXXMMMM`|`MMMMMMMM`|`MMMMMMMM`|...|`MMMMMMMM`|
|double-extended-precision|`SXXXXXXX`|`XXXXXXXX`|`1MMMMMMM`|`MMMMMMMM`|...|`MMMMMMMM`|

`S` Stellt das Vorzeichenbit der `X`des Exponentenbits die unausgewogene, und die `M`des sind die Bits der Mantisse. Beachten Sie, dass das höchstwertige Bit davon ausgegangen, in den Formaten mit einfacher Genauigkeit und mit doppelter Genauigkeit dass wird, aber als "1" in das Format des erweiterten-mit doppelter Genauigkeit 3 Byte vorhanden ist.

Um der binärpunkt ordnungsgemäß zu verschieben, Sie zuerst den Exponenten Binärkomma und klicken Sie dann der binärpunkt nach rechts verschieben oder links die entsprechende Anzahl von Bits.

## <a name="special-values"></a>Spezielle Werte

Der Gleitkomma-Formate enthalten einige Werte, die besonders behandelt werden.

### <a name="zero"></a>Zero

0 (null) kann nicht normalisiert werden, wodurch sie nicht darstellbaren in der normalisierten Form eines Werts mit einfacher Genauigkeit oder mit doppelter Genauigkeit. Ein spezieller Bitmuster der ausschließlich Nullen stellt 0 dar. Es ist auch möglich darstellen – 0 als 0 (null), mit dem Anmeldenamen-Bit festgelegt ist, sondern - 0 und 0. Vergleich immer gleich.

### <a name="infinities"></a>Unendliche

Die + ∞ und −∞ Werte werden durch einen Exponenten mit ausschließlich Einsen und einer Mantisse des ausschließlich Nullen dargestellt. Positive und negative unendliche können mit das signierte Bit dargestellt werden.

### <a name="subnormals"></a>Subnormals

Es ist möglich, viele kleinere Größe als die kleinste normalisierte Anzahl darstellen. Diese Nummern werden als bezeichnet *subnormal* oder *denormal* Zahlen. Wenn der Exponent ausschließlich Nullen ist, und die Mantisse nicht 0 (null ist), gilt implizite führende Bit der Mantisse 0 (null), nicht. Die Genauigkeit der subnormal Zahlen fällt aus, wie die Anzahl der führenden Nullen in der Mantisse steigt.

### <a name="nan---not-a-number"></a>NaN - keine Zahl

Es ist möglich, Werte darstellen, die keine reelle Zahl, z. B. 0 / 0, in der IEEE-Gleitkomma-Format. Der Wert dieser Art wird aufgerufen, eine *NaN*. Ein NaN-Wert wird durch ein Exponent, der ausschließlich Einsen und eine nicht-NULL-Mantisse dargestellt. Es gibt zwei Typen von NaNs, *quiet* NaN-Werte oder QNaNs, und *signalisiert* NaN-Werte oder SNaNs. Quiet-NaNs haben einen führenden in die Mantisse und weitergegeben werden in der Regel durch einen Ausdruck. Sie stellen einen unbestimmten Wert ein, z. B. das Ergebnis der Division durch unendlich oder Multiplizieren von unendlich mit 0 (null) dar. Datagrammkanal NaNs haben eine führende 0 (null) in die Mantisse. Diese werden für Vorgänge verwendet, die nicht gültig ist, um eine Gleitkommazahl Hardwareausnahme zu signalisieren.

## <a name="examples"></a>Beispiele

Im folgenden sind einige Beispiele mit einfacher Genauigkeit, Format:

- Für den Wert 2 das signierte Bit ist 0 (null), und der gespeicherte Exponent 128 oder 1000 0000 in Binärdatei ist 127 plus 1. Die gespeicherte binäre Mantisse ist (1). 000 0000 0000 0000 0000 0000, die eine implizite führende 1 und binäre verweisen, damit die tatsächliche Mantisse ist.

   |Wert|Formel|Binäre Darstellung|Hexadezimal|
   |-|-|-|-|
   |2|1 * 2<sup>1</sup>|0100 0000 0000 0000 0000 0000 0000 0000|0x40000000|

- Der Wert-2. Entspricht + 2, mit dem Unterschied, dass das signierte Bit festgelegt ist. Dies gilt auch für den negativen Wert, der alle IEEE Format Gleitkommazahlen.

   |Wert|Formel|Binäre Darstellung|Hexadezimal|
   |-|-|-|-|
   |-2|-1 * 2<sup>1</sup>|1100 0000 0000 0000 0000 0000 0000 0000|0xC0000000|

- Der Wert 4. Dieselbe Signifikanden, Exponent wird um eine erhöht (gewichteter Wert ist 129 oder 100 0000 1 im Binärformat.

   |Wert|Formel|Binäre Darstellung|Hexadezimal|
   |-|-|-|-|
   |4|1 * 2<sup>2</sup>|0100 0000 1000 0000 0000 0000 0000 0000|0x40800000|

- Der Wert 6. Derselbe Exponent, der Signifikanden ist größer, um die Hälfte – (1). 100 0000 ... 0000 0000, da dies einen Binärbruch ist ist, die 1 1/2, da die Werte der die Dezimalstellen 1/2, 1/4, 1/8 usw. sind.

   |Wert|Formel|Binäre Darstellung|Hexadezimal|
   |-|-|-|-|
   |6|1.5 * 2<sup>2</sup>|0100 0000 1100 0000 0000 0000 0000 0000|0x40C00000|

- Der Wert 1. Gleiche Signifikanden als andere Potenzen von 2, der gewichtete Exponent ist jeweils unter zwei als 127 oder binär 011 1111 1.

   |Wert|Formel|Binäre Darstellung|Hexadezimal|
   |-|-|-|-|
   |1|1 * 2<sup>0</sup>|0011 1111 1000 0000 0000 0000 0000 0000|0x3F800000|

- Der Wert 0,75. Der gewichtete Exponent ist 126 011 1111 0 binär, und die Mantisse ist (1). 100 0000 ... 0000 0000, ist das, 1 1/2.

   |Wert|Formel|Binäre Darstellung|Hexadezimal|
   |-|-|-|-|
   |0.75|1.5 * 2<sup>-1</sup>|0011 1111 0100 0000 0000 0000 0000 0000|0x3F400000|

- Der Wert 2.5. Genau wie zwei, außer wird das Bit, das 1/4 stellt in der Mantisse festgelegt.

   |Wert|Formel|Binäre Darstellung|Hexadezimal|
   |-|-|-|-|
   |2.5|1.25 * 2<sup>1</sup>|0100 0000 0010 0000 0000 0000 0000 0000|0x40200000|

- 1/10 ist eine sich wiederholende Bruchzahl im Binärformat. Die Mantisse ist knapp 1,6, und der gewichtete Exponent besagt, dass 1,6 x 16. geteilt werden soll (es ist binär, d.h. 123, in Dezimalstellen 011 1101 1). Der Exponent "true" ist 123-127 = - 4, was bedeutet, dass der Faktor, mit dem multipliziert 2<sup>-4</sup> = 1/16. Beachten Sie, die die gespeicherte Mantisse in der letzte Aspekt aufgerundet wird — beim Versuch, die nicht darstellbare Anzahl so genau wie möglich darzustellen. (Der Grund, 1/10 "und" 1/100 sind in Binärdatei nicht exakt darstellbar ist vergleichbar mit der Grund für das 1/3 nicht exakt darstellbar ist, als Dezimalzahl ist.)

   |Wert|Formel|Binäre Darstellung|Hexadezimal|
   |-|-|-|-|
   |0.1|1.6 * 2<sup>-4</sup>|0011 1101 1100 1100 1100 1100 1100 1101|0x3DCCCCCD|

- 0 (null) ist ein Sonderfall, der ausschließlich Nullen ist die Formel für den minimal möglichen darstellbaren positive Wert, verwendet.

   |Wert|Formel|Binäre Darstellung|Hexadezimal|
   |-|-|-|-|
   |0|1 * 2<sup>-128</sup>|0000 0000 0000 0000 0000 0000 0000 0000|0x00000000|

## <a name="see-also"></a>Siehe auch

[Warum Gleitkommazahlen an Genauigkeit verlieren können](why-floating-point-numbers-may-lose-precision.md)