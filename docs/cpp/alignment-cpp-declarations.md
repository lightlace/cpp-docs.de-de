---
title: (Ausrichtung (c++ Deklarationen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: a986d510-ccb8-41f8-b905-433df9183485
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5248d7c692e3443ea0e0798cf723f38099c3f863
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2018
ms.locfileid: "42571947"
---
# <a name="alignment-c-declarations"></a>Ausrichtung (C++-Deklarationen)
Eine der Funktionen von C++ auf niedriger Ebene ist die Möglichkeit zum Angeben der präzisen Ausrichtung von Objekten im Speiche, um eine bestimmte Hardwarearchitektur optimal zu nutzen. Standardmäßig richtet der Compiler Klassen- und Strukturmember Elemente auf ihren Größenwert aus: Bool und Char werden an ein Byte-Grenzen ausgerichtet, short an zwei-Byte, Int an vier-Byte, long long, double und long double an acht-Byte. In den meisten Szenarien müssen Sie sich nie mit der Ausrichtung befassen, da die Standardausrichtung bereits optimal ist. In einigen Fällen jedoch erzielen Sie bedeutende Leistungsverbesserungen oder Speicherplatzeinsparungen, indem Sie eine benutzerdefinierte Ausrichtung für Ihre Datenstrukturen angeben. Vor Visual Studio 2015 konnten Sie die Microsoft-spezifischen Schlüsselwörter __alignof und declspec(alignas) verwenden, um eine Ausrichtung anzugeben, die größer als der Standardwert ist. Starten Sie in Visual Studio 2015 sollten die C ++ 11-Standardschlüsselwörter verwenden [Alignof und Alignas](../cpp/alignof-and-alignas-cpp.md) für maximale Codeportabilität. Die neuen Schlüsselwörter verhalten sich wie die Microsoft-spezifischen Erweiterungen, und die Dokumentation für diese Erweiterungen gilt auch für die neuen Schlüsselwörter. Finden Sie unter [__alignof-Operator](../cpp/alignof-operator.md) und [ausrichten](../cpp/align-cpp.md) für Weitere Informationen. Der C++-Standard kein Packverhalten für die Ausrichtung an Grenzen, die kleiner als die Standardeinstellung des Compilers für die Zielplattform, daher Sie weiterhin mithilfe des Microsoft #pragma müssen [Pack](../preprocessor/pack.md) in diesem Fall.  
  
 Die C++-Standardbibliothek bietet die [Aligned_storage-Klasse](../standard-library/aligned-storage-class.md) zur Zuteilung von Arbeitsspeicher für Datenstrukturen mit benutzerdefinierten Ausrichtungen und die [Aligned_union-Klasse](../standard-library/aligned-union-class.md) zum Angeben der Ausrichtung für Unions mit nicht trivialen Konstruktoren oder Destruktoren.  
  
## <a name="about-alignment"></a>Infos zur Ausrichtung  
 Die Ausrichtung ist eine Eigenschaft einer Speicheradresse, ausgedrückt als numerisches Adressmodulo der Potenz 2. Beispielsweise ist die Adresse 0x0001103F modulo 4 gleich 3. Diese Adresse wird als 4n+3 ausgerichtet bezeichnet, wobei 4 die gewählte Potenz von 2 angibt. Die Ausrichtung einer Adresse hängt von der ausgewählten Zweierpotenz ab. Das gleiche Adressmodulo 8 ist 7. Eine Adresse wird als an X ausgerichtet betrachtet, wenn die Ausrichtung Xn+ 0 ist.  
  
 CPUs führen Anweisungen für Daten im Arbeitsspeicher aus, und die Daten werden anhand ihrer Adresse im Speicher identifiziert. Zusätzlich zur Adresse hat ein einzelnes Datum auch eine Größe. Ein Datum wird als natürlich ausgerichteten bezeichnet, wenn seine Adresse auf die Größe ausgerichtet und andernfalls nicht ausgerichtet ist. Ein 8-Byte-Gleitkommazahl-Datum ist beispielsweise natürlich ausgerichtet, wenn die Adresse, die zur Identifizierung verwendet wird, auf 8 ausgerichtet ist.  
  
 Gerätecompiler versuchen, Daten auf eine Weise zuzuordnen, die eine Fehlausrichtung der Daten verhindert.  
  
 Der Compiler weist für einfache Datentypen Adressen zu, die ein Vielfaches der Größe in Bytes des Datentyps entsprechen. Folglich weist der Compiler Adressen zu Variablen vom Typ long zu, die ein Vielfaches von vier sind, und legt die unteren beiden Bits der Adresse auf null fest.  
  
 Darüber hinaus füllt der Compiler Strukturen auf eine Weise, die jedes Element der Struktur natürlich ausrichtet. Sehen Sie sich die Struktur „struct x_“ im folgenden Codebeispiel an:  
  
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
  
 Im folgenden Codebeispiel wird veranschaulicht, wie der Compiler die aufgefüllte Struktur in „memory:Copy“ platziert.  
  
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
  
1.  Beiden Deklarationen geben „sizeof(struct x_)“ als 12 Bytes zurück.  
  
2.  Die zweite Deklaration enthält zwei Auffüllelemente:  
  
3.  char _pad0[3] zum Ausrichten des int-b-Members an eine Vier-Byte-Grenze  
  
4.  char _pad1[1] zum Ausrichten der Arrayelemente der Struktur „struct _x bar[3]“  
  
5.  Die Auffüllung richtet die Elemente von „bar[3]“ in einer Weise aus, die natürlichen Zugriff ermöglicht.  
  
 Im folgenden Codebeispiel wird die Verwendung des bar[3]-Arraylayouts veranschaulicht.  
  
```  
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
 [Datenstrukturausrichtung](http://en.wikipedia.org/wiki/Data_structure_alignment)