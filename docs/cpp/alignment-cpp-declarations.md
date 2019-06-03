---
title: Ausrichtung (C++-Deklarationen)
description: Wie die datenausrichtung in Modern angegeben ist C++.
ms.date: 05/30/2019
ms.assetid: a986d510-ccb8-41f8-b905-433df9183485
ms.openlocfilehash: b6e03ac2b89624a0eb6602183d4ff4bf8b518f8d
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450771"
---
# <a name="alignment-c-declarations"></a>Ausrichtung (C++-Deklarationen)

Eines der Features von C++ auf niedriger Ebene ist die Möglichkeit zum Angeben der präzisen Ausrichtung von Objekten im Speiche, um eine bestimmte Hardwarearchitektur optimal zu nutzen. Standardmäßig richtet der Compiler Klassen- und Strukturmember Elemente auf ihren Größenwert: `bool` und `char` an 1-Byte-Grenzen `short` an 2-Byte-Grenzen `int`, `long`, und `float` auf 4-Byte-Begrenzungen und `long long`, `double`, und `long double` auf 8-Byte-Begrenzungen. In den meisten Szenarien müssen Sie nie mit der Ausrichtung befassen, da die standardausrichtung bereits optimal ist. In einigen Fällen jedoch erreichen bedeutende leistungsverbesserungen oder speicherplatzeinsparungen, Sie durch eine benutzerdefinierte Ausrichtung für Ihre Datenstrukturen angeben. Bevor Sie Visual Studio 2015 können Sie die Microsoft-spezifische Schlüsselwörter `__alignof` und `declspec(alignas)` eine Ausrichtung, die größer als der Standardwert an. Starten Sie in Visual Studio 2015 sollten die C ++ 11-Standardschlüsselwörter verwenden [Alignof und Alignas](../cpp/alignof-and-alignas-cpp.md) für maximale Codeportabilität. Die neuen Schlüsselwörter Verhalten sich wie in die Hintergründe der Microsoft-spezifische Erweiterungen. Die Dokumentation für diese Erweiterungen gilt auch für die neuen Schlüsselwörter. Weitere Informationen finden Sie unter [__alignof-Operator](../cpp/alignof-operator.md) und [ausrichten](../cpp/align-cpp.md). Die C++ Standard nicht Packverhalten für die Ausrichtung an Grenzen, die kleiner als die Standardeinstellung des Compilers für die Zielplattform, daher Sie weiterhin mithilfe des Microsoft #pragma müssen [Pack](../preprocessor/pack.md) in diesem Fall.

Verwenden der [Aligned_storage-Klasse](../standard-library/aligned-storage-class.md) für speicherbelegung von Datenstrukturen mit benutzerdefinierten Ausrichtungen. Die [Aligned_union-Klasse](../standard-library/aligned-union-class.md) wird zum Angeben der Ausrichtung für Unions mit nicht trivialen Konstruktoren oder Destruktoren.

## <a name="about-alignment"></a>Infos zur Ausrichtung

Die Ausrichtung ist eine Eigenschaft einer Speicheradresse, ausgedrückt als numerisches Adressmodulo der Potenz 2. Beispielsweise ist die Adresse 0x0001103F modulo 4 3. Diese Adresse wird als 4n + 3, wobei 4 die gewählte Potenz von 2 angibt ausgerichtet werden. Die Ausrichtung einer Adresse hängt davon ab, für die gewählte Potenz von 2. Das gleiche Adressmodulo 8 ist 7. Eine Adresse wird als an X ausgerichtet betrachtet, wenn die Ausrichtung Xn+ 0 ist.

CPUs führen Anweisungen, die ausgeführt werden, auf Daten im Arbeitsspeicher gespeichert. Die Daten werden anhand ihrer Adresse im Speicher identifiziert. Ein einzelnes Datum hat auch eine Größe aus. Wir bezeichnen ein Datum *natürlich ausgerichtet* wenn seine Adresse auf die Größe ausgerichtet ist. Es heißt *falsch ausgerichtete* andernfalls. Eine 8-Byte-Gleitkommazahl-Datum ist beispielsweise natürlich ausgerichtet, besitzt die Adresse, die zur Identifizierung verwendet eine 8-Byte-Ausrichtung.

## <a name="compiler-handling-of-data-alignment"></a>Compilerfehler Behandlung der datenausrichtung

Compiler versucht, die Zuordnungen der Daten auf eine Weise zu machen, die einer verhindert.

Der Compiler weist für einfache Datentypen Adressen zu, die ein Vielfaches der Größe in Bytes des Datentyps entsprechen. Beispielsweise weist der Compiler Adressen zu Variablen vom Typ `long` , die ein Vielfaches von 4 hat das Festlegen der unteren 2 Bits der Adresse 0 (null) sind.

Der Compiler füllt auch Strukturen in einer Weise, die jedes Element der Struktur natürlich ausrichtet. Betrachten Sie die Struktur `struct x_` im folgenden Codebeispiel wird:

```cpp
struct x_
{
   char a;     // 1 byte
   int b;      // 4 bytes
   short c;    // 2 bytes
   char d;     // 1 byte
} MyStruct;
```

Der Compiler füllt die Struktur, um die natürliche Ausrichtung zu erzwingen.

Im folgenden Codebeispiel wird veranschaulicht, wie der Compiler die aufgefüllte Struktur im Arbeitsspeicher platziert:

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
}
```

1. Zurückgeben von beiden Deklarationen `sizeof(struct x_)` als 12 Bytes.

1. Die zweite Deklaration enthält zwei Auffüllelemente:

1. `char _pad0[3]` Anpassung an die `int b` Member auf 4-Byte-Begrenzung

1. `char _pad1[1]` Ausrichten der Arrayelemente der Struktur `struct _x bar[3];`

1. Die Auffüllung richtet die Elemente der `bar[3]` in einer Weise, die natürlichen Zugriff ermöglicht.

Das folgende Codebeispiel zeigt die `bar[3]` Arraylayouts:

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

[Datenstrukturausrichtung](https://en.wikipedia.org/wiki/Data_structure_alignment)
