---
title: Konvertierungen von Gleitkommatypen
ms.date: 10/02/2019
helpviewer_keywords:
- converting floating point
- floating-point conversion
ms.assetid: 96804c8e-fa3b-4742-9006-0082ed9e57f2
ms.openlocfilehash: c2f7c25015b36545f969796a1f85d355d715427a
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998714"
---
# <a name="conversions-from-floating-point-types"></a>Konvertierungen von Gleitkommatypen

Ein Gleit Komma Wert, der in einen anderen Gleit kommatyp konvertiert wird, wird nicht geändert, wenn der ursprüngliche Wert exakt im Ergebnistyp dargestellt werden kann. Wenn der ursprüngliche Wert numerisch ist, aber nicht exakt darstellbar ist, ist das Ergebnis entweder der nächste höhere oder nächste niedrigere darstellbare Wert. Weitere Informationen finden Sie unter [Grenzwerte für Gleit Komma Konstanten](../c-language/limits-on-floating-point-constants.md) für den Bereich von Gleit Komma Typen.

Ein Gleit Komma Wert, der in einen ganzzahligen Typ konvertiert wird, wird zuerst abgeschnitten, indem ein beliebiger Bruch Wert verworfen wird. Wenn dieser gekürzte Wert im Ergebnistyp darstellbar ist, muss das Ergebnis dieser Wert sein. Wenn Sie nicht Darstell Bar ist, ist der Ergebniswert nicht definiert.

**Microsoft-spezifisch**

Microsoft-Compiler verwenden IEEE-754 binary32-Darstellung für **float** -Werte und binary64-Darstellung für **long Double** und **Double**. Da **long Double** und **Double** dieselbe Darstellung verwenden, haben Sie denselben Bereich und dieselbe Genauigkeit.

Wenn der Compiler eine **Double** -oder **long Double** -Gleit Komma Zahl in einen **float**-Wert konvertiert, wird das Ergebnis gemäß den Gleit Komma-Umgebungs Steuerelementen gerundet, die standardmäßig "Round to Next, Ties to even" sind. Wenn ein numerischer Wert zu hoch oder zu niedrig ist, um **als numerischer** Gleit Komma Wert dargestellt zu werden, ist das Konvertierungsergebnis gemäß dem Vorzeichen des ursprünglichen Werts positiv oder minus unendlich. wenn diese Option aktiviert ist, wird eine Überlauf Ausnahme ausgelöst.

Beim Konvertieren in ganzzahlige Typen ist das Ergebnis einer Konvertierung in einen Typ, der kleiner als **Long** ist, das Ergebnis der Konvertierung des Werts in **Long**und das anschließende Konvertieren in den Ergebnistyp.

Für die Konvertierung in ganzzahlige Typen, die mindestens so groß wie **lang**sind, kann eine Konvertierung eines Werts, der zu hoch oder zu niedrig ist, um im Ergebnistyp darzustellen, einen der folgenden Werte zurückgeben:

- Das Ergebnis kann ein *Sentinelwert*sein, bei dem es sich um den darstellbaren Wert von 0 (null) handelt. Bei signierten Typen ist dies der niedrigste darstellbare Wert (0x800... 0). Bei nicht signierten Typen ist dies der höchste darstellbare Wert (0xFF... F).

- Das Ergebnis kann über *lastet sein,* wobei Werte zu hoch für die Darstellung in den höchsten darstellbaren Wert konvertiert werden und dass zu niedrige Werte in den niedrigsten darstellbaren Wert konvertiert werden. Einer dieser beiden Werte wird auch als Sentinel-Wert verwendet.

- Bei der Konvertierung **in eine lange** oder **unsignierte**Länge ohne Vorzeichen ist das Ergebnis der Konvertierung eines Werts außerhalb des gültigen Bereichs möglicherweise ein anderer Wert als der höchste oder niedrigste darstellbare Wert. Ob das Ergebnis ein Sentinelwert oder ein gesichtter Wert ist, hängt von den Compileroptionen und der Zielarchitektur ab. Zukünftige compilerreleases können stattdessen einen satten Wert oder einen Sentinelwert zurückgeben.

**Ende Microsoft-spezifisch**

In der folgenden Tabelle werden die Konvertierungen von Gleitkommatypen zusammengefasst.

## <a name="table-of-conversions-from-floating-point-types"></a>Tabelle der Konvertierungen von Gleit Komma Typen

|Von|Beschreibung|Methode|
|----------|--------|------------|
|**float**|**char**|Konvertieren in **long**; Konvertieren von **long** in **char**|
|**float**|**short**|Konvertieren in **long**; Konvertieren von **long** in **short**|
|**float**|**int**|Beim Dezimaltrennzeichen abschneiden. Wenn das Ergebnis zu groß ist, um als **int**dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**float**|**long**|Beim Dezimaltrennzeichen abschneiden. Wenn das Ergebnis zu groß ist, um als **long** dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**float**|**langes long**|Beim Dezimaltrennzeichen abschneiden. Wenn das Ergebnis zu groß ist, um als **Long**-Wert dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**float**|**unsigned char**|Konvertieren in **Long**; Konvertieren von **Long** in **Ganzzahl ohne Vorzeichen char**|
|**float**|**unsigned short**|Konvertieren in **long**; Konvertieren von **long** in **unsigned short**|
|**float**|**unsigned**|Beim Dezimaltrennzeichen abschneiden. Wenn das Ergebnis zu groß ist, um als **nicht signiertes**dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**float**|**unsigned long**|Beim Dezimaltrennzeichen abschneiden. Wenn das Ergebnis zu groß ist, um als **Ganzzahl ohne Vorzeichen long**-Wert dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**float**|**Ganzzahl ohne Vorzeichen long long**|Beim Dezimaltrennzeichen abschneiden. Wenn das Ergebnis zu groß ist, um als **Ganzzahl ohne Vorzeichen long long**-Wert dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**float**|**double**|Stellt als **Double**dar.|
|**float**|**long double**|Stellt als **long Double**dar.|
|**double**|**char**|Konvertieren in **float**; Konvertieren von **float** in **char**|
|**double**|**short**|Konvertieren in **float**; Konvertieren von **float** in **short**|
|**double**|**int**|Beim Dezimaltrennzeichen abschneiden. Wenn das Ergebnis zu groß ist, um als **int**dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**double**|**long**|Beim Dezimaltrennzeichen abschneiden. Wenn das Ergebnis zu groß ist, um als **long** dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**double**|**unsigned char**|Konvertieren in **Long**; Konvertieren von **Long** in **Ganzzahl ohne Vorzeichen char**|
|**double**|**unsigned short**|Konvertieren in **long**; Konvertieren von **long** in **unsigned short**|
|**double**|**unsigned**|Beim Dezimaltrennzeichen abschneiden. Wenn das Ergebnis zu groß ist, um als **nicht signiertes**dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**double**|**unsigned long**|Beim Dezimaltrennzeichen abschneiden. Wenn das Ergebnis zu groß ist, um als **Ganzzahl ohne Vorzeichen long**-Wert dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**double**|**Ganzzahl ohne Vorzeichen long long**|Beim Dezimaltrennzeichen abschneiden. Wenn das Ergebnis zu groß ist, um als **Ganzzahl ohne Vorzeichen long long**-Wert dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**double**|**float**|Darstellen als **float**. Wenn der **Double** -Wert nicht exakt als **float**dargestellt werden kann, tritt ein Genauigkeits Verlust auf. Wenn der Wert zu groß ist, um als **float** dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**double**|**long double**|Der Wert **long double** wird als **double** behandelt.|

Konvertierungen von **long Double** folgen derselben Methode wie Konvertierungen von **Double**.

## <a name="see-also"></a>Siehe auch

[Zuweisungs Konvertierungen](../c-language/assignment-conversions.md)
