---
title: Compilerwarnung (Stufe 2) C4275
ms.date: 02/08/2019
f1_keywords:
- C4275
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
ms.openlocfilehash: 6e0e80d465d77bd4fe99fbcaa98e289b8a4c8b63
ms.sourcegitcommit: 966e4466f10c93fc12faf33d28e03b39489423fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2019
ms.locfileid: "55987026"
---
# <a name="compiler-warning-level-2-c4275"></a>Compilerwarnung (Stufe 2) C4275

> nicht - DLL-Schnittstelle Klasse*Klasse_1*"verwendet als Basis für die DLL-Schnittstelle, Klasse"*Klasse_2*"

Eine exportierte Klasse wurde von einer Klasse abgeleitet, die exportiert wurde nicht.

Um das Risiko einer datenbeschädigung zu minimieren, beim Exportieren einer Klasse mit [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), stellen Sie sicher, dass:

- Alle statischen Daten erfolgt über Funktionen, die aus der DLL exportiert werden.

- Keine Inline-Methoden der Klasse können statische Daten ändern.

- Verwenden Sie keine Inline-Methoden der Klasse CRT-Funktionen oder andere Library-Funktionen, die statische Daten verwenden.

- Keine Inline Klassenfunktionen verwenden Sie CRT-Funktionen oder anderen Bibliotheksfunktionen zur, in denen Sie Zugriff auf statische Daten.

- Keine Methoden der Klasse (unabhängig vom inlining) können Typen verwenden, in dem die Instanziierung in der EXE- und DLL statische Datenunterschiede aufweisen.

Sie können vermeiden, Exportieren von Klassen definieren, die eine DLL, die definiert eine Klasse mit virtuellen Funktionen und Funktionen Sie aufrufen kann, instanziieren und Löschen von Objekten des Typs.  Sie können dann virtuelle Funktionen nur für den Typ aufrufen.

C4275 können in Visual C++ ignoriert werden, wenn Sie von einem Typ in der C++-Standardbibliothek, die eine Debugversion kompilieren (**/MTd**) und, in dem die Fehlermeldung des Compilers auf `_Container_base`.

```cpp
// C4275.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275
```