---
title: Parameterübergabe
ms.date: 11/04/2016
ms.assetid: e838ee5f-c2fe-40b0-9a23-8023c949c820
ms.openlocfilehash: 1b7fb126ab3b140d0ab672067df35c5fc8df926e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648746"
---
# <a name="parameter-passing"></a>Parameterübergabe

Die ersten vier Ganzzahlargumente werden an Register übergeben. Ganzzahlige Werte werden (in der Reihenfolge von links nach rechts) in den Registern RCX, RDX, R8 und R9 übergeben. Argumente 5 und höher auf dem Stapel übergeben. Sind alle Argumente in Registern rechts ausgerichtet. Auf diese Weise können der aufgerufene die höherwertigen Bits des Registers Wenn ignorieren muss sein und können nur den Teil der erforderlichen Registrierung zugreifen.

Gleitkomma und doppelter Genauigkeit-Argumente übergeben werden, in XMM0: XMM3 (bis zu 4) mit den Integer-Slot (RCX, RDX, R8 und R9), die normalerweise für Sie, dass das cardinal Slot verwendet wird, ignoriert (siehe Beispiel) und umgekehrt.

[__m128](../cpp/m128.md) Typen, Arrays und Zeichenfolgen werden nicht sofort als Wert übergeben, sondern stattdessen ein Zeiger auf vom Aufrufer zugeordneten Speicher übergeben wird. Strukturen oder Unions von Größe, 8, 16, 32 oder 64 Bits und __m64 werden übergeben, als wären sie ganze Zahlen mit derselben Größe. Strukturen oder Unions, als diese Größen werden als Zeiger auf vom Aufrufer zugeordneten Speicher übergeben. Für diese Aggregattypen als Zeiger übergeben (einschließlich \__m128), die vom Aufrufer reservierte temporäre Speicher werden 16-Byte-ausgerichtet.

Intrinsische Funktionen, die Stapelspeicher ist nicht zugeordnet werden, und rufen Sie keine anderen Funktionen können andere volatile Register verwenden, um zusätzliche Registerargumente zu übergeben, da eine enge Bindung zwischen dem Compiler und die Implementierung der systeminternen Funktion vorhanden ist. Dies ist eine weitere Möglichkeit zur Verbesserung der Leistung.

Der aufgerufene ist dafür verantwortlich, sichern die Registerparameter in der Schattenkopie-Speicherplatz bei Bedarf.

Die folgende Tabelle fasst zusammen, wie Parameter übergeben werden:

|Parametertyp|Wie übergebenen|
|--------------------|----------------|
|Gleitkomma|Erste 4 Parameter - XMM0 bis XMM3. Andere Benutzer übergeben an den Stapel.|
|Ganze Zahl|Zuerst 4 Parameter – RCX, RDX, R8 R9. Andere Benutzer übergeben an den Stapel.|
|Aggregate (8, 16, 32 oder 64-Bit) und __m64|Zuerst 4 Parameter – RCX, RDX, R8 R9. Andere Benutzer übergeben an den Stapel.|
|Aggregate (Sonstiges)|Der vom Zeiger. Erste 4 Parameter, die als Zeiger in den Registern RCX, RDX, R8 und R9 übergeben|
|__m128|Der vom Zeiger. Erste 4 Parameter, die als Zeiger in den Registern RCX, RDX, R8 und R9 übergeben|

## <a name="example-of-argument-passing-1---all-integers"></a>Beispiel 1: alle ganzen Zahlen für die Argumentübergabe

```
func1(int a, int b, int c, int d, int e);
// a in RCX, b in RDX, c in R8, d in R9, e pushed on stack
```

## <a name="example-of-argument-passing-2---all-floats"></a>Beispiel 2: alle float-Elemente für die Argumentübergabe

```
func2(float a, double b, float c, double d, float e);
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, e pushed on stack
```

## <a name="example-of-argument-passing-3---mixed-ints-and-floats"></a>Beispiel 3 – gemischte ganz- und Gleitkommazahlen für die Argumentübergabe

```
func3(int a, double b, int c, float d);
// a in RCX, b in XMM1, c in R8, d in XMM3
```

## <a name="example-of-argument-passing-4--m64-m128-and-aggregates"></a>Beispiel 4 für die Argumentübergabe-__m64, \__m128, und Aggregate

```
func4(__m64 a, _m128 b, struct c, float d);
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3
```

## <a name="see-also"></a>Siehe auch

[Aufrufkonvention](../build/calling-convention.md)