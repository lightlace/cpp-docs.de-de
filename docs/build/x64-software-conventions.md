---
title: X64 Softwarekonventionen
ms.date: 12/17/2018
helpviewer_keywords:
- x64 coding conventions
- Visual C++, x64 calling conventions
ms.assetid: 750f3d97-1706-4840-b2fc-41a007329a08
ms.openlocfilehash: 11d29b6c31ccecfe5b9c51c2f9311213bd4a6732
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62313827"
---
# <a name="x64-software-conventions"></a>X64 Softwarekonventionen

In diesem Abschnitt wird beschrieben, die C++-Konvention Methodik für X64, der 64-Bit-Erweiterung für die X86 aufrufen Architektur.

## <a name="overview-of-x64-calling-conventions"></a>Übersicht über die X64 Aufrufkonventionen

Zwei wichtige Unterschiede zwischen X86- und X64 werden die 64-Bit-Adressierung-Funktion und ein Satz von 16 64-Bit-Flatfile zur allgemeinen Verwendung registriert. Bei Verwendung der erweiterten Register-Gruppe, X64 verwendet werden. die [__fastcall](../cpp/fastcall.md) Aufrufkonvention und ein Ausnahmebehandlungsmodell RISC-basierten. Die `__fastcall` Konvention verwendet führt die Registrierung für die ersten vier Argumente und den Stapelrahmen, um zusätzliche Argumente übergeben. Für Informationen zu den X64 Aufrufkonvention, einschließlich registernutzung, die Parameter Stapel, zurückgeben, Werte und stapelentladung, finden Sie unter [X64 Aufrufkonvention](x64-calling-convention.md).

## <a name="enable-optimization-for-x64"></a>Optimierung für X64 aktivieren

Die folgende Compileroption können Sie Ihre Anwendung für X64 zu optimieren:

- [/favor (Für Architektureigenschaften optimieren)](../build/reference/favor-optimize-for-architecture-specifics.md)

## <a name="types-and-storage"></a>Typen und Speicher

In diesem Abschnitt wird beschrieben, die Enumeration und Speicherung von Datentypen für die X64 Architektur.

### <a name="scalar-types"></a>skalare Typen

Obwohl es möglich, den Zugriff auf Daten mit einer Ausrichtung ist, wird empfohlen, Ausrichten von Daten für die natürliche Grenze oder ein Vielfaches, um Leistungseinbußen zu vermeiden. Enumerationen sind Konstante ganze Zahlen und fungieren als 32-Bit-Ganzzahlen. Die folgende Tabelle beschreibt die Typdefinition und empfohlene Speicher für Daten, Bezug auf die Ausrichtung, die mithilfe der folgenden Ausrichtungswerte:

- Byte - 8-Bit

- Word - 16-Bit

- Zeigt Doppelwort - 32-Bit

- Vierfachwort - 64-Bit

- Octaword - 128-Bit

|||||
|-|-|-|-|
|Skalaren Typ|C-Datentyp|Speichergröße (in Byte)|Empfohlene Ausrichtung|
|**INT8**|**char**|1|Byte|
|**UINT8**|**unsigned char**|1|Byte|
|**INT16**|**short**|2|Word|
|**UINT16**|**unsigned short**|2|Word|
|**INT32**|**int**, **long**|4|Doubleword|
|**UINT32**|**ganze Zahl ohne Vorzeichen, unsigned long**|4|Doubleword|
|**INT64**|**__int64**|8|Quadword|
|**UINT64**|**__int64 ohne Vorzeichen**|8|Quadword|
|**FP32-Vorgänge (einfache Genauigkeit)**|**float**|4|Doubleword|
|**FP64 (doppelte Genauigkeit)**|**double**|8|Quadword|
|**ZEIGER**|__\*__|8|Quadword|
|**__m64**|**struct __m64**|8|Quadword|
|**__m128**|**struct __m128**|16|Octaword|

### <a name="aggregates-and-unions"></a>Aggregate und unions

Andere Typen wie Arrays, Strukturen und Unions, gelten strengere Ausrichtung, die die konsistente aggregieren und union-Speicher und Datenabruf zu gewährleisten. Hier sind die Definitionen für Arrays, Struktur und Union:

- Array

   Enthält eine geordnete Gruppe von benachbarten Datenobjekten. Jedes Objekt wird aufgerufen, eine *Element*. Alle Elemente in einem Array haben die gleiche Größe und Datentyp.

- Struktur

   Enthält eine geordnete Gruppe von Datenobjekten. Im Gegensatz zu den Elementen eines Arrays können die Datenobjekte in einer Struktur unterschiedlichen Typen und Größen haben. Jedes Datenobjekt in einer Struktur wird aufgerufen, eine *Member*.

- Union

   Ein Objekt, das eine benannte Elemente enthält. Die Elemente der benannten Menge können einen beliebigen Typ sein. Der Speicher zugewiesen werden, damit eine Union ist der Speicherbedarf für den größten Member dieser Union zuzüglich möglicher Abstände, die erforderlich sind, für die Ausrichtung gleich.

Die folgende Tabelle zeigt die empfohlene Ausrichtung für die skalaren Member von Unions und Strukturen.

||||
|-|-|-|
|Skalaren Typ|C-Datentyp|Erforderlichen Ausrichtung ergibt|
|**INT8**|**char**|Byte|
|**UINT8**|**unsigned char**|Byte|
|**INT16**|**short**|Word|
|**UINT16**|**unsigned short**|Word|
|**INT32**|**int**, **long**|Doubleword|
|**UINT32**|**ganze Zahl ohne Vorzeichen, unsigned long**|Doubleword|
|**INT64**|**__int64**|Quadword|
|**UINT64**|**__int64 ohne Vorzeichen**|Quadword|
|**FP32-Vorgänge (einfache Genauigkeit)**|**float**|Doubleword|
|**FP64 (doppelte Genauigkeit)**|**double**|Quadword|
|**ZEIGER**|<strong>\*</strong>|Quadword|
|**__m64**|**struct __m64**|Quadword|
|**__m128**|**struct __m128**|Octaword|

Die folgenden aggregierten Ausrichtung Regeln gelten:

- Die Ausrichtung eines Arrays ist identisch mit die Ausrichtung eines der Elemente des Arrays.

- Die Ausrichtung des Anfangs einer Struktur oder Union ist die maximale Ausrichtung eines einzelnen Member. Jedes Element in der Struktur oder Union muss korrekt ausgerichtet platziert werden, gemäß der vorstehenden Tabelle ist möglicherweise eine implizite interne Abstände, je nachdem das vorherige Element erforderlich.

- Die Größe der Struktur muss ein ganzzahliges Vielfaches seiner Ausrichtung Abstand hinter das letzte Element ist möglicherweise erforderlich. Da Strukturen und Unions in Arrays gruppiert werden können, muss jedes Arrayelement eine Struktur oder Union beginnen und enden auf die richtige Ausrichtung, die zuvor ermittelt.

- Es ist möglich, Ausrichten von Daten in so, dass der ausrichtungsanforderungen größer sein, solange alle zuvor genannten Regeln verwaltet werden.

- Ein einzelner Compiler kann die Komprimierung einer Struktur aus Gründen der Größe anpassen. Z. B. [/Zp (Strukturmemberausrichtung)](../build/reference/zp-struct-member-alignment.md) ermöglicht das Anpassen der Komprimierung von Strukturen.

### <a name="examples-of-structure-alignment"></a>Beispiele für die Strukturausrichtung

Die folgenden vier Beispielen wird jeweils deklarieren, dass eine ausgerichtete Struktur oder Union und die entsprechenden Zahlen veranschaulichen das Layout der Struktur oder Union im Arbeitsspeicher. Jede Spalte in einer Abbildung stellt ein Byte Arbeitsspeicher und die Anzahl in der Spalte gibt an, die Verschiebung dieser Bytes. Der Name in der zweiten Zeile von jeder Abbildung entspricht dem Namen einer Variablen in der Deklaration. Die schattierten Spalten anzugeben, dass die Auffüllung, die erforderlich ist, um die angegebene Ausrichtung zu erzielen.

#### <a name="example-1"></a>Beispiel 1

```C
// Total size = 2 bytes, alignment = 2 bytes (word).

_declspec(align(2)) struct {
    short a;      // +0; size = 2 bytes
}
```

![AMD Konvertierung Beispiel 1 Strukturlayout](../build/media/vcamd_conv_ex_1_block.png "Strukturlayout für AMD Konvertierung Beispiel 1")

#### <a name="example-2"></a>Beispiel 2

```C
// Total size = 24 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) struct {
    int a;       // +0; size = 4 bytes
    double b;    // +8; size = 8 bytes
    short c;     // +16; size = 2 bytes
}
```

![AMD Konvertierung Beispiel 2 Strukturlayout](../build/media/vcamd_conv_ex_2_block.png "Strukturlayout für AMD Konvertierung Beispiel 2")

#### <a name="example-3"></a>Beispiel 3

```C
// Total size = 12 bytes, alignment = 4 bytes (doubleword).

_declspec(align(4)) struct {
    char a;       // +0; size = 1 byte
    short b;      // +2; size = 2 bytes
    char c;       // +4; size = 1 byte
    int d;        // +8; size = 4 bytes
}
```

![AMD Konvertierung Beispiel 2 Strukturlayout](../build/media/vcamd_conv_ex_3_block.png "Strukturlayout für AMD Konvertierung Beispiel 2")

#### <a name="example-4"></a>Beispiel 4

```C
// Total size = 8 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) union {
    char *p;      // +0; size = 8 bytes
    short s;      // +0; size = 2 bytes
    long l;       // +0; size = 4 bytes
}
```

![AMD Konvertierung Beispiel 4 union Layouit](../build/media/vcamd_conv_ex_4_block.png "AMD Konvertierung Beispiel 4 union Layouit")

### <a name="bitfields"></a>Bitfelder

Struktur-Bitfelder sind auf 64-Bit beschränkt und kann vom Typ signiert Int "," unsigned Int "," int64 "oder" nicht-signierter int64. Bitfelder, die die Typgrenze überschreiten, werden Bits das Bitfeld der Ausrichtung der nächsten Typ ausrichten übersprungen. Beispielsweise können ganzzahlige Bitfeldern keine 32-Bit-überschreiten.

### <a name="conflicts-with-the-x86-compiler"></a>Verursacht einen Konflikt mit der X86 Compiler

Datentypen, die größer als 4 Byte auf dem Stapel nicht automatisch ausgerichtet werden, bei der Verwendung der X86 Compiler zum Kompilieren einer Anwendung. Da die Architektur für die X86 Compiler kann ein 4-Byte-ausgerichtete-Stapel an, etwas größer als 4 Bytes, z. B. eine 64-Bit-Ganzzahl, kann nicht in eine 8-Byte-Adresse automatisch ausgerichtet werden.

Arbeiten mit einer nicht ausgerichteten Daten hat zwei Auswirkungen.

- Es dauert möglicherweise länger, nicht ausgerichtete Speicherorte zuzugreifen, als auf ausgerichtete.

- Nicht ausgerichtete Speicherorte können nicht in interlocked-Vorgänge verwendet werden.

Wenn Sie eine strengere Ausrichtung benötigen, verwenden Sie `__declspec(align(N))` Ihre Variablendeklarationen. Dies bewirkt, dass den Compiler an, dass dynamisch im Stapel, um Ihren Spezifikationen zu erfüllen. Allerdings kann die dynamische Anpassung des Stapels zur Laufzeit langsamer Ausführung der Anwendung führen.

## <a name="register-usage"></a>Registerverwendung

Die Architektur bietet für 16 allgemeinen Registern (im folgenden als Ganzzahl-Register bezeichnet) sowie von 16 XMM/YMM X64 registriert Gleitkommaregister zur Verfügung. Volatile Register sind Scratch-Register, von denen der Aufrufer voraussetzt, dass sie während eines Aufrufs zerstört werden. Nicht volatile Register müssen ihre Werte über einen Funktionsaufruf hinweg bewahren und, sofern sie verwendet werden, vom Aufgerufenen gespeichert werden.

### <a name="register-volatility-and-preservation"></a>Gibt die Volatilität und Beibehaltung der registrieren

Die folgende Tabelle beschreibt, wie jedes Register bei Funktionsaufrufen verwendet wird:

||||
|-|-|-|
|Register|Status|Mit|
|RAX|Volatil|Rückgabewert-Register|
|RCX|Volatil|Erstes Ganzzahl-Argument|
|RDX|Volatil|Zweites Ganzzahl-Argument|
|R8|Volatil|Drittes Ganzzahl-Argument|
|R9|Volatil|Viertes Ganzzahl-Argument|
|R10:R11|Volatil|Muss je nach Anforderung des Aufrufers bewahrt werden. Wird in syscall-/sysret-Instruktionen verwendet.|
|R12:R15|Nicht volatil|Muss vom Aufgerufenen bewahrt werden|
|RDI|Nicht volatil|Muss vom Aufgerufenen bewahrt werden|
|RSI|Nicht volatil|Muss vom Aufgerufenen bewahrt werden|
|RBX|Nicht volatil|Muss vom Aufgerufenen bewahrt werden|
|RBP|Nicht volatil|Kann als Frame-Pointer verwendet werden; muss vom Aufgerufenen bewahrt werden|
|RSP|Nicht volatil|Stack-Pointer|
|XMM0, YMM0|Volatil|Erstes FP-Argument; erstes Vektortypargument, wenn `__vectorcall` verwendet wird|
|XMM1, YMM1|Volatil|Zweites FP-Argument; zweites Argument vom Typ Vektor, wenn `__vectorcall` verwendet wird|
|XMM2, YMM2|Volatil|Drittes FP-Argument; drittes Argument vom Typ Vektor, wenn `__vectorcall` verwendet wird|
|XMM3, YMM3|Volatil|Viertes FP-Argument; viertes Argument vom Typ Vektor, wenn `__vectorcall` verwendet wird|
|XMM4, YMM4|Volatil|Muss je nach Bedarf vom Aufrufer bewahrt werden; fünftes Argument vom Typ Vektor, wenn `__vectorcall` verwendet wird|
|XMM5, YMM5|Volatil|Muss je nach Bedarf vom Aufrufer bewahrt werden; sechstes Argument vom Typ Vektor, wenn `__vectorcall` verwendet wird|
|XMM6:XMM15, YMM6:YMM15|Nicht volatil (XMM), Volatil (obere Hälfte von YMM)|Muss vom aufgerufenen bewahrt werden. YMM-Register müssen je nach Bedarf vom Aufrufer bewahrt werden.|

Bei Funktionsende und Funktion-Eintrags, der C-Laufzeitbibliothek-Aufrufe und Aufrufe der Windows-System, das Richtungsflag in der CPU Flags registrieren soll gelöscht werden.

## <a name="stack-usage"></a>Verwendung von Stapeln

Einzelheiten der stapelreservierung "," Ausrichtung "," Funktionstypen "und" Stapelrahmen in X64 finden Sie unter [X64 stack Nutzung](stack-usage.md).

## <a name="prolog-and-epilog"></a>Prolog und epilog

Jede Funktion, die Stapelspeicher zuweist, andere Funktionen aufruft, nicht flüchtigen Register gespeichert oder mithilfe der Ausnahmebehandlung benötigen ein Prologs, deren Adresse Grenzwerte im Zusammenhang mit der Tabelleneintrag für die jeweilige Funktion und epilogen am Entladedaten beschrieben werden jeder Beendigung einer Funktion. Weitere Informationen zu den erforderlichen Prolog und Epilogcode auf X64, finden Sie unter [X64 Prolog und Epilog](prolog-and-epilog.md).

## <a name="x64-exception-handling"></a>X64 Behandlung von Ausnahmen

Informationen zu den Konventionen und die Datenstrukturen verwendet, um strukturierte Ausnahmebehandlung und C++-Ausnahmebehandlung Verhalten für die X64 implementieren, finden Sie unter [X64 Ausnahmebehandlung](exception-handling-x64.md).

## <a name="intrinsics-and-inline-assembly"></a>Systeminterne Funktionen und Inline-assembly

Eine der Einschränkungen für die X64 Compiler nicht Inline-Assembler unterstützt werden. Dies bedeutet, die, die Funktionen, kann nicht in C oder C++ geschrieben werden, entweder als Unterroutinen oder als systeminterne Funktionen, die vom Compiler unterstützt geschrieben werden müssen. Bestimmte Funktionen sind leistungsabhängig, andere hingegen nicht. Leistungsorientierte Funktionen sollte als systeminterne Funktionen implementiert werden.

Die systeminternen Funktionen, die vom Compiler unterstützt werden, werden in beschrieben [intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md).

## <a name="image-format"></a>Bildformat

Die X64 ausführbares Image-Format je typu PE32 +. Ausführbare Images (DLLs und EXEs) sind auf eine Maximalgröße von 2 GB beschränkt, sodass relative Adressierung mit einer 32-Bit-Verschiebung verwendet werden kann, statisches Bild Datenadresse. Diese Daten umfassen die Importadresstabelle, Zeichenfolgenkonstanten, statischen globalen Daten und So weiter.

## <a name="see-also"></a>Siehe auch

[Aufrufkonventionen](../cpp/calling-conventions.md)
