---
title: X64 Aufrufkonvention
description: Details zu den standardmäßigen X64 ABI-Aufrufkonvention.
ms.date: 12/17/2018
ms.assetid: 41ca3554-b2e3-4868-9a84-f1b46e6e21d9
ms.openlocfilehash: 02bf4719766366049b600b148ad88fc238f4e54e
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415784"
---
# <a name="x64-calling-convention"></a>X64 Aufrufkonvention

Dieser Abschnitt beschreibt die Standardprozesse und Konventionen, die eine Funktion (Aufrufer) verwendet wird, um Aufrufe in einer anderen Funktion (die aufgerufene) in X64 Code.

## <a name="calling-convention-defaults"></a>Aufrufen von Konvention-Standardeinstellungen

Standardmäßig verwendet die X64 verwendeten Application Binary Interface (ABI) eine vier-Register Aufrufkonvention Fast-Aufruf durch. Speicherplatz wird in der Aufrufliste als Schattenkopien Speicher für den aufgerufenen zum Speichern dieser Register zugeordnet. Es gibt strict eins zu eins entsprechen zwischen den Argumenten auf ein Funktionsaufruf und die für diese Argumente zu verwendenden Register ein. Ein der Argumente, das 8 Bytes passt nicht oder ist nicht 1, 2, 4 oder 8 Bytes muss als Verweis übergeben werden. Ein einzelnes Argument ist nicht auf mehrere Register verteilt. Die X87 Registerstapel wird nicht verwendet, und kann von der aufgerufenen Instanz verwendet werden, jedoch müssen bei Funktionsaufrufen flüchtige berücksichtigt werden. Alle Gleitkommawerte Vorgänge erfolgen mithilfe der 16 XMM-Register. Es werden ganzzahlige Argumente in Registern RCX, RDX, R8 und R9 übergeben. Gleitkommaoptionen XMM0L, XMM1L, XMM2L und XMM3L Argumente übergeben werden. 16-Byte-Argumente werden als Verweis übergeben. Übergeben von Parametern ist ausführlich im [Parameterübergabe](#parameter-passing). Zusätzlich zu diesen Registerkarten RAX, R10, R11, XMM4 und XMM5 flüchtige gelten. Alle anderen Register sind nicht flüchtig. Registernutzung wird ausführlich dokumentiert [Verwendung registrieren](../build/x64-software-conventions.md#register-usage) und [Aufrufer-/Aufgerufener gespeichert registriert](#callercallee-saved-registers).

Für Funktionen mit Prototyp werden alle Argumente in welche erwarteten aufgerufenen vor der Übergabe konvertiert. Der Aufrufer ist für die datenträgerzuweisung für Parameter an den aufgerufenen verantwortlich und muss immer ausreichend Speicherplatz zum Speichern von vier Registerparameter zuordnen, auch wenn der aufgerufene viele Parameter verwendet werden. Diese Konvention vereinfacht die Unterstützung für die Programmiersprache C Funktionen ohne Prototyp und Vararg-C/C++-Funktionen. Für Vararg-ohne Prototyp-Funktionen Gleitkommawerte müssen Werte, die in der entsprechenden Allzweckregister dupliziert werden. Alle Parameter über die ersten vier müssen auf dem Stapel gespeichert werden, nachdem der Schatten speichern, vor dem Aufruf. Vararg-Funktion Informationen finden Sie [Varargs](#varargs). Ohne Prototyp-Funktionsinformationen finden Sie im [Funktionen ohne Prototyp](#unprototyped-functions).

## <a name="alignment"></a>Ausrichtung

Die meisten Strukturen werden gemäß ihrer natürlichen Ausrichtung ausgerichtet. Die wichtigsten Ausnahmen sind der Stapelzeiger und `malloc` oder `alloca` Arbeitsspeicher, die auf 16-Byte-ausgerichtet werden, um Leistung zu unterstützen. Ausrichtung auf mehr als 16 Bytes muss manuell durchgeführt werden, aber da es 16 Bytes handelt es sich um eine Ausrichtung-Standardgröße für XMM-Vorgänge, sollte dieser Wert für die meisten Code funktionieren. Weitere Informationen zur Struktur Layout- und ausrichtungsverwaltung finden Sie unter [Typen und Speicher](../build/x64-software-conventions.md#types-and-storage). Weitere Informationen über das Layout der Stack finden Sie unter [X64 stack Nutzung](../build/stack-usage.md).

## <a name="unwindability"></a>Unwindability

Funktionen sind Funktionen, die alle nicht flüchtigen Register nicht ändern. Eine innerer-Funktion kann nicht flüchtigen RSP, z. B. ändern, durch Aufrufen einer Funktion oder das Zuordnen von zusätzlichen Stapelspeicher für lokale Variablen. Um nicht flüchtigen Register wiederherzustellen, wenn eine Ausnahme behandelt wird, müssen der nichtblatt-Funktionen mit statischen Daten kommentiert werden, die beschreibt, wie Sie zu die Funktion an eine beliebige Anweisung ordnungsgemäß zu entladen. Diese Daten werden gespeichert, als *Pdata*, oder Prozedur Daten bezieht sich wiederum auf *Xdata*, die Daten für die Ausnahmebehandlung. Die Xdata enthält Informationen, die entladen und auf zusätzliche Pdata bzw. eine ausnahmehandlerfunktion verweisen. Prologe und Epiloge sind sehr eingeschränkten, damit sie ordnungsgemäß in Xdata beschrieben werden können. Der Stapelzeiger muss auf 16 Bytes in einer beliebigen Region Code ausgerichtet werden, die nicht im Rahmen eines Prolog oder Epilog mit Ausnahme von Funktionen. Funktionen können entladen werden, indem Sie einfach eine Rückgabe simuliert, sodass Pdata und Xdata nicht erforderlich sind. Weitere Informationen über die richtige Struktur von Funktion prologen und epilogen, finden Sie unter [X64 Prolog und Epilog](../build/prolog-and-epilog.md). Weitere Informationen zur Behandlung von Ausnahmen und die Behandlung von Ausnahmen und stapelentladung Pdata und Xdata finden Sie unter [X64 Ausnahmebehandlung](../build/exception-handling-x64.md).

## <a name="parameter-passing"></a>Parameterübergabe

Die ersten vier Ganzzahlargumente werden an Register übergeben. Ganzzahlige Werte werden in links-nach-rechts-Reihenfolge, in Registern RCX, RDX, R8 und R9, übergeben. Argumente 5 und höher auf dem Stapel übergeben. Alle Argumente sind rechtsbündig in Registern, damit der aufgerufene die höherwertigen Bits des Registers zu ignorieren und nur den Teil der erforderlichen Registrierung zugreifen kann.

Alle Argumente Gleitkomma und doppelter Genauigkeit in den ersten vier Parametern werden in XMM0: XMM3, je nach Position übergeben. Die Ganzzahlregister RCX, RDX, R8 und R9, die normalerweise für diese Positionen verwendet wird, werden ignoriert, außer bei Varargs-Argumente. Weitere Informationen finden Sie unter [Varargs](#varargs). Auf ähnliche Weise die XMM0: XMM3 Register ignoriert werden, wenn das entsprechende Argument eine ganze Zahl oder einen Zeiger-Typ ist.

[__m128](../cpp/m128.md) Typen, Arrays und Zeichenfolgen werden nicht sofort als Wert übergeben. Stattdessen wird ein Zeiger auf vom Aufrufer zugeordneten Speicher übergeben. Strukturen und Unions Größe 8, 16, 32 oder 64 Bits und __m64-Typen werden übergeben, als wären sie ganze Zahlen mit derselben Größe. Strukturen oder Unions von anderen Größen werden als Zeiger auf vom Aufrufer zugeordneten Speicher übergeben. Für diese Aggregattypen, übergeben als ein Zeiger ist einschließlich \__m128, die vom Aufrufer reservierte temporäre Speicher muss 16-Byte-ausgerichtet sein.

Intrinsische Funktionen, die nicht Stapelspeicher reservieren, und rufen Sie andere Funktionen nicht verwenden gelegentlich andere volatile Register, um zusätzliche Registerargumente übergeben. Diese Optimierung wird durch die enge Bindung zwischen dem Compiler und die Implementierung der systeminternen Funktion ermöglicht.

Der aufgerufene ist verantwortlich für die Ausgabe die Registerparameter in der Schattenkopie-Speicherplatz bei Bedarf.

Die folgende Tabelle fasst zusammen, wie Parameter übergeben werden:

|Parametertyp|Wie übergebenen|
|--------------------|----------------|
|Gleitkomma|Erste 4 Parameter - XMM0 bis XMM3. Andere Benutzer übergeben an den Stapel.|
|Ganze Zahl|Zuerst 4 Parameter – RCX, RDX, R8 R9. Andere Benutzer übergeben an den Stapel.|
|Aggregate (8, 16, 32 oder 64-Bit) und __m64|Zuerst 4 Parameter – RCX, RDX, R8 R9. Andere Benutzer übergeben an den Stapel.|
|Aggregate (Sonstiges)|Der vom Zeiger. Erste 4 Parameter, die als Zeiger in den Registern RCX, RDX, R8 und R9 übergeben|
|__m128|Der vom Zeiger. Erste 4 Parameter, die als Zeiger in den Registern RCX, RDX, R8 und R9 übergeben|

### <a name="example-of-argument-passing-1---all-integers"></a>Beispiel 1: alle ganzen Zahlen für die Argumentübergabe

```cpp
func1(int a, int b, int c, int d, int e);
// a in RCX, b in RDX, c in R8, d in R9, e pushed on stack
```

### <a name="example-of-argument-passing-2---all-floats"></a>Beispiel 2: alle float-Elemente für die Argumentübergabe

```cpp
func2(float a, double b, float c, double d, float e);
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, e pushed on stack
```

### <a name="example-of-argument-passing-3---mixed-ints-and-floats"></a>Beispiel 3 – gemischte ganz- und Gleitkommazahlen für die Argumentübergabe

```cpp
func3(int a, double b, int c, float d);
// a in RCX, b in XMM1, c in R8, d in XMM3
```

### <a name="example-of-argument-passing-4--m64-m128-and-aggregates"></a>Beispiel 4 für die Argumentübergabe-__m64, \__m128, und Aggregate

```cpp
func4(__m64 a, _m128 b, struct c, float d);
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3
```

## <a name="varargs"></a>VarArgs

Wenn Parameter über Varargs (z. B. mit den Auslassungspunkten Argumente) übergeben werden, gilt die normale Registrierung Parameterübergabe-Konvention, einschließlich der fünften und nachfolgende Argumente an den Stapel übertragen. Es ist die aufgerufene Dump-Argumente, die deren Adresse akzeptiert haben. Nur Gleitkommawerte darf sowohl ganzzahligen Register und die Gleitkommaregister den Wert für den Fall, dass der aufgerufene den Wert in die Ganzzahlregister erwartet.

## <a name="unprototyped-functions"></a>Funktionen ohne Prototyp

Für Funktionen, die nicht vollständige Prototypen übergibt der Aufrufer ganzzahlige Werte als ganze Zahlen und Gleitkommazahlen-Punktwerte als mit doppelter Genauigkeit. Nur Gleitkommawerte enthalten sowohl ganzzahligen Register und die Gleitkommaregister den Float-Wert für den Fall, dass der aufgerufene den Wert in die Ganzzahlregister erwartet.

```cpp
func1();
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7
   func1(2, 1.0, 7);
}
```

## <a name="return-values"></a>Rückgabewert

Ein skalarer Rückgabewert, der in 64 Bits passen kann durch RAX zurückgegeben. Dies schließt auch __m64-Typen. Nicht skalare Typen, darunter Gleitkommazahlen, Doubles und vektortypen, wie z. B. [__m128](../cpp/m128.md), [__m128i](../cpp/m128i.md), [__m128d](../cpp/m128d.md) werden in XMM0 zurückgegeben. Der Status von nicht verwendeten Bits in dem in RAX oder XMM0 zurückgegebenen Wert ist nicht definiert.

Benutzerdefinierte Typen können als Wert von globalen Funktionen und statische Memberfunktionen zurückgegeben werden. Um einen benutzerdefinierten Typ als Wert in RAX zurückgegeben werden, müssen sie eine Länge von 1, 2, 4, 8, 16, 32 oder 64 Bits. Außerdem benötigen sie keinen benutzerdefinierten Konstruktor, Destruktor oder Kopierzuweisungsoperator; keine privaten oder geschützten nicht statischen Datenmember; Geben Sie keine nicht statischen Datenmember des Verweistyps; keine Basisklassen; keine virtuellen Funktionen; und keine Datenmember, die diese Anforderungen nicht ebenfalls erfüllen. (Dies ist im Grunde die Definition eines C++03 POD-Typs. Da die Definition im standard C ++ 11 geändert wurde, es wird nicht empfohlen `std::is_pod` für diesen Test.) Andernfalls nimmt der Aufrufer die Verantwortung für die Speicherbelegung und für die Übergabe eines Zeigers für den Rückgabewert als erstes Argument an. Nachfolgende Argumente werden dann um ein Argument nach rechts verschoben. Derselbe Zeiger muss vom Aufgerufenen in RAX zurückgegeben werden.

Diese Beispiele zeigen, wie Parameter und Rückgabewerte für Funktionen mit den angegebenen Deklarationen übergeben werden:

### <a name="example-of-return-value-1---64-bit-result"></a>Beispiel für Rückgabewert 1 – Ergebnis 64-bit

```Output
__int64 func1(int a, float b, int c, int d, int e);
// Caller passes a in RCX, b in XMM1, c in R8, d in R9, e pushed on stack,
// callee returns __int64 result in RAX.
```

### <a name="example-of-return-value-2---128-bit-result"></a>Beispiel für Rückgabewert 2 – Ergebnis 128-bit

```Output
__m128 func2(float a, double b, int c, __m64 d);
// Caller passes a in XMM0, b in XMM1, c in R8, d in R9,
// callee returns __m128 result in XMM0.
```

### <a name="example-of-return-value-3---user-type-result-by-pointer"></a>Beispiel für Rückgabewert 3 – Ergebnis Benutzertyp als Zeiger

```Output
struct Struct1 {
   int j, k, l;    // Struct1 exceeds 64 bits.
};
Struct1 func3(int a, double b, int c, float d);
// Caller allocates memory for Struct1 returned and passes pointer in RCX,
// a in RDX, b in XMM2, c in R9, d pushed on the stack;
// callee returns pointer to Struct1 result in RAX.
```

### <a name="example-of-return-value-4---user-type-result-by-value"></a>Beispiel für Rückgabewert 4 – Ergebnis Benutzertyp als Wert

```Output
struct Struct2 {
   int j, k;    // Struct2 fits in 64 bits, and meets requirements for return by value.
};
Struct2 func4(int a, double b, int c, float d);
// Caller passes a in RCX, b in XMM1, c in R8, and d in XMM3;
// callee returns Struct2 result by value in RAX.
```

## <a name="callercallee-saved-registers"></a>Gespeicherte Register von Aufrufer/Aufgerufener

Die Register RAX, RCX, RDX, R8, R9, R10, R11 als flüchtig gelten und berücksichtigt werden muss zerstört, auf den Funktionsaufrufen (es sei denn, andernfalls Sicherheit, belegbare durch Analyse, wie z. B. die Optimierung des ganzen Programms).

Die Register RBX, RBP, RDI, RSI, RSP, R12, R13, R14 und R15 werden als permanenten betrachtet und müssen gespeichert werden und wiederhergestellt, indem eine Funktion, die verwendet werden.

## <a name="function-pointers"></a>Funktionszeiger

Funktionszeiger sind einfach Zeiger auf die Bezeichnung der jeweiligen Funktion. Es ist kein Inhalt (TOC)-Anforderungen für Funktionszeiger.

## <a name="floating-point-support-for-older-code"></a>Gleitkommaunterstützung für älteren code

MMX und Gleitkommastapel Register (MM0-MM7/ST0-ST7) werden für Kontextwechsel beibehalten. Es gibt keine explizite Aufrufkonvention für diese Register. Die Verwendung von diese Register wird im Kernelmoduscode streng untersagt.

## <a name="fpcsr"></a>FpCsr

Der Registerstatus enthält auch die X87 FPU-Steuerwort. Die Aufrufkonvention schreibt vor, diese registrieren, um nicht flüchtig sein.

Ausführung des Programms die X87 FPU-Steuerelement Word Register ist am Anfang auf die folgenden Standardwerte festgelegt:

| Registrieren Sie\[Bits] | Einstellung |
|-|-|
| FPCSR\[0:6] | Ausnahme maskiert alle 1 (alle Ausnahmen maskiert) |
| FPCSR\[7] | Reserviert – 0 |
| FPCSR\[8:9] | Precision-Steuerung - 10 b (doppelte Genauigkeit) |
| FPCSR\[10:11] | Rundung Steuerelement - 0 (round auf die nächste) |
| FPCSR\[12] | Unendlichkeitssteuerung - 0 (nicht verwendet) |

Eine aufgerufene Funktion, die eines der Felder in FPCSR ändert, muss diese vor der Rückgabe an den Aufrufer wiederherstellen. Darüber hinaus muss ein Aufrufer, der keines dieser Felder geändert wurde wiederhergestellt werden ihren Standardwerten vor dem eine aufgerufene Funktion aufrufen, es sei denn, der Vereinbarung der aufgerufenen Funktion die geänderten Werte erwartet wird.

Es gibt zwei Ausnahmen auf die Regeln über die Flüchtigkeit der Steuerelement-Kennzeichen:

1. In Funktionen, in dem dokumentiert die angegebene Funktion dient, nicht flüchtiger FpCsr-flags.

1. Wenn Programmanalyse korrigieren Sie, dass die Verletzung der Regeln in einem Programm, die verhält sich genauso wie ein Programm führt, in denen diese Regeln, z. B. durch Analyse des gesamten Programms verletzt werden.

## <a name="mxcsr"></a>MxCsr

Der Registerstatus enthält auch MxCsr. Die Aufrufkonvention teilt dieses Register, in einen flüchtigen und einen nicht flüchtigen Teil. Der flüchtige Teil besteht aus sechs Status-Flags, im MXCSR\[0:5], zwar die restlichen das MXCSR-Register\[6:15], gilt als nicht flüchtig.

Der Teil wird zu Beginn der Ausführung des Programms auf die folgenden Standardwerte festgelegt:

| Registrieren Sie\[Bits] | Einstellung |
|-|-|
| MXCSR\[6] | Denormals werden Nullen - 0 |
| MXCSR\[7:12] | Ausnahme maskiert alle 1 (alle Ausnahmen maskiert) |
| MXCSR\[13:14] | Rundung Steuerelement - 0 (round auf die nächste) |
| MXCSR\[15] | Leeren Sie 0 (null) für maskierte Unterlauf - 0 (deaktiviert) |

Eine aufgerufene Funktion, die die nicht flüchtige Felder im MXCSR ändert, muss diese vor der Rückgabe an den Aufrufer wiederherstellen. Darüber hinaus muss ein Aufrufer, der keines dieser Felder geändert wurde wiederhergestellt werden ihren Standardwerten vor dem eine aufgerufene Funktion aufrufen, es sei denn, der Vereinbarung der aufgerufenen Funktion die geänderten Werte erwartet wird.

Es gibt zwei Ausnahmen auf die Regeln über die Flüchtigkeit der Steuerelement-Kennzeichen:

- In Funktionen, in dem dokumentiert die angegebene Funktion dient, nicht flüchtiger MxCsr-flags.

- Wenn Programmanalyse korrigieren Sie, dass die Verletzung der Regeln in einem Programm, die verhält sich genauso wie ein Programm führt, in denen diese Regeln, z. B. durch Analyse des gesamten Programms verletzt werden.

Keine Annahmen können über den Status des flüchtigen Teils des MXCSR funktionsübergreifend, vorgenommen werden, es sei denn, insbesondere in der Dokumentation der Funktion beschrieben.

## <a name="setjmplongjmp"></a>setjmp/longjmp

Wenn Sie die setjmpex.h oder setjmp.h einschließen, alle Aufrufe von [Setjmp](../c-runtime-library/reference/setjmp.md) oder [Longjmp](../c-runtime-library/reference/longjmp.md) führen eine Entladung, die Destruktoren aufruft und `__finally` aufrufen.  Dies unterscheidet sich von X86, in denen führt auch setjmp.h `__finally` Klauseln und -Destruktoren nicht aufgerufen wird.

Ein Aufruf von `setjmp` behält den aktuellen Stack-Pointer, nicht flüchtigen Register und MxCsr-Register.  Aufrufe von `longjmp` zurück zum zuletzt `setjmp` aufrufen, Standort und setzt die Stack-Pointer, nicht flüchtigen Register und MxCsr registriert, in den Zustand wie durch die die letzte beibehalten `setjmp` aufrufen.

## <a name="see-also"></a>Siehe auch

[Softwarekonventionen bei x64-Systemen](../build/x64-software-conventions.md)
