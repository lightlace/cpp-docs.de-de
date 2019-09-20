---
title: Ausrichtung (C++-Deklarationen)
description: Gibt an, wie die Daten Ausrichtung C++in modern angegeben wird.
ms.date: 09/19/2019
ms.assetid: a986d510-ccb8-41f8-b905-433df9183485
ms.openlocfilehash: 67debc00343b8bee4184e020c9269011e2fcebc9
ms.sourcegitcommit: f907b15f50a6b945d0b87c03af0050946157d701
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "71158754"
---
# <a name="alignment-c-declarations"></a>Ausrichtung (C++-Deklarationen)

Eines der Features von C++ auf niedriger Ebene ist die Möglichkeit zum Angeben der präzisen Ausrichtung von Objekten im Speiche, um eine bestimmte Hardwarearchitektur optimal zu nutzen. Standardmäßig richtet der Compiler Klassen-und Strukturmember auf ihren Größen Wert aus: `bool` und `char` an 1-Byte-Begrenzungen `short` , an 2-Byte- `int`Begrenzungen `long`,, `float` und an 4-Byte-Grenzen und `long long`, undan`long double` 8-Byte-Begrenzungen. `double` In den meisten Szenarien müssen Sie sich nicht mit der Ausrichtung beschäftigen, da die Standardausrichtung bereits optimal ist. In einigen Fällen können Sie jedoch bedeutende Leistungsverbesserungen oder Speicher Einsparungen erzielen, indem Sie eine benutzerdefinierte Ausrichtung für Ihre Datenstrukturen angeben. Vor Visual Studio 2015 konnten Sie die Microsoft-spezifischen Schlüsselwörter `__alignof` verwenden `declspec(alignas)` und eine Ausrichtung angeben, die größer als die Standardeinstellung ist. Ab Visual Studio 2015 sollten Sie die Standard Schlüsselwörter " [alignof" und "alignas](../cpp/alignof-and-alignas-cpp.md) " für "c++ 11" verwenden, um die maximale Portabilität Die neuen Schlüsselwörter Verhalten sich auf die gleiche Weise wie die Microsoft-spezifischen Erweiterungen. Die Dokumentation für diese Erweiterungen gilt auch für die neuen Schlüsselwörter. Weitere Informationen finden Sie unter [__alignof-Operator](../cpp/alignof-operator.md) und [Ausrichtung](../cpp/align-cpp.md). Der C++ Standard gibt kein Verpackungs Verhalten für die Ausrichtung an Grenzen an, die kleiner als der Compilerstandard für die Zielplattform sind, sodass Sie in diesem Fall weiterhin das Microsoft #Pragma [Pack](../preprocessor/pack.md) verwenden müssen.

Verwenden Sie die [aligned_storage-Klasse](../standard-library/aligned-storage-class.md) für die Speicher Belegung von Datenstrukturen mit benutzerdefinierten Ausrichtungen. Die [aligned_union-Klasse](../standard-library/aligned-union-class.md) dient zum Angeben der Ausrichtung für Unions mit nicht trivialen Konstruktoren oder Dekonstruktoren.

## <a name="about-alignment"></a>Infos zur Ausrichtung

Die Ausrichtung ist eine Eigenschaft einer Speicheradresse, ausgedrückt als numerisches Adressmodulo der Potenz 2. Beispielsweise ist die Adresse 0x0001103f modulo 4 3. Diese Adresse wird als "4N + 3" ausgerichtet, wobei "4" die gewählte Potenz von 2 angibt. Die Ausrichtung einer Adresse hängt von der gewählten Potenz von 2 ab. Das gleiche Adressmodulo 8 ist 7. Eine Adresse wird als an X ausgerichtet betrachtet, wenn die Ausrichtung Xn+ 0 ist.

CPUs führen Anweisungen aus, die für im Arbeitsspeicher gespeicherte Daten verwendet werden. Die Daten werden durch Ihre Adressen im Arbeitsspeicher identifiziert. Ein einzelnes Datum weist auch eine Größe auf. Wir nennen ein Datum, das *natürlich ausgerichtet* ist, wenn seine Adresse auf seine Größe abgestimmt ist. Andernfalls wird Sie als *falsch ausgerichtet* bezeichnet. Beispielsweise ist ein 8-Byte-Gleit Komma Datum natürlich ausgerichtet, wenn die Adresse, die zur Identifizierung verwendet wird, eine 8-Byte-Ausrichtung hat.

## <a name="compiler-handling-of-data-alignment"></a>Compilerbehandlung der Daten Ausrichtung

Compiler versuchen, Daten Zuordnungen auf eine Weise zu erstellen, die eine Fehlausrichtung der Daten verhindert.

Der Compiler weist für einfache Datentypen Adressen zu, die ein Vielfaches der Größe in Bytes des Datentyps entsprechen. Der Compiler weist z. b. Adressen Variablen vom Typ `long` zu, die ein Vielfaches von 4 sind, wobei die untersten Bits der Adresse auf 0 (null) festgelegt werden.

Der Compiler füllt auch Strukturen auf eine Weise auf, die jedes Element der Struktur auf natürliche Weise anpasst. Sehen Sie sich `struct x_` die Struktur im folgenden Codebeispiel an:

```cpp
struct x_
{
   char a;     // 1 byte
   int b;      // 4 bytes
   short c;    // 2 bytes
   char d;     // 1 byte
} bar[3];
```

Der Compiler füllt die Struktur, um die natürliche Ausrichtung zu erzwingen.

Im folgenden Codebeispiel wird gezeigt, wie der Compiler die aufgefüllte Struktur in den Arbeitsspeicher platziert:

```cpp
// Shows the actual memory layout
struct x_
{
   char a;            // 1 byte
   char _pad0[3];     // padding to put 'b' on 4-byte boundary
   int b;            // 4 bytes
   short c;          // 2 bytes
   char d;           // 1 byte
   char _pad1[1];    // padding to make sizeof(x_) multiple of 4
} bar[3];
```

Beide Deklarationen `sizeof(struct x_)` geben als 12 Bytes zurück.

Die zweite Deklaration enthält zwei Auffüllelemente:

1. `char _pad0[3]`, wenn der `int b` Member an einer 4-Byte-Grenze ausgerichtet werden soll.

1. `char _pad1[1]`, wenn die Array Elemente der-Struktur `struct _x bar[3];` an einer vier-Byte-Grenze ausgerichtet werden sollen.

Der Abstand richtet die Elemente von auf eine `bar[3]` Weise aus, die natürlichen Zugriff zulässt.

Das folgende Codebeispiel zeigt das `bar[3]` Array Layout:

```Output
adr offset   element
------   -------
0x0000   char a;         // bar[0]
0x0001   char pad0[3];
0x0004   int b;
0x0008   short c;
0x000a   char d;
0x000b   char _pad1[1];

0x000c   char a;         // bar[1]
0x000d   char _pad0[3];
0x0010   int b;
0x0014   short c;
0x0016   char d;
0x0017   char _pad1[1];

0x0018   char a;         // bar[2]
0x0019   char _pad0[3];
0x001c   int b;
0x0020   short c;
0x0022   char d;
0x0023   char _pad1[1];
```

## <a name="see-also"></a>Siehe auch

[Ausrichtung der Datenstruktur](https://en.wikipedia.org/wiki/Data_structure_alignment)
