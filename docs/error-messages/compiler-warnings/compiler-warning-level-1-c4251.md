---
title: Compilerwarnung (Stufe 1) C4251
ms.date: 11/04/2016
f1_keywords:
- C4251
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
ms.openlocfilehash: d2fff1d2f30c4ac80af6d5b9ca452fa5f30f5a15
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207349"
---
# <a name="compiler-warning-level-1-c4251"></a>Compilerwarnung (Stufe 1) C4251

'Bezeichner': Klasse 'Typ' Dll-Schnittstelle, von der Klasse "Typ2" verwendet werden muss

Um das Risiko einer datenbeschädigung zu minimieren, beim Exportieren einer Klasse mit [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), sicher, dass:

- Alle statischen Daten ist der Zugriff über Funktionen, die aus der DLL exportiert werden.

- Keine Inline-Methoden der Klasse können statische Daten ändern.

- Keine Inline-Methoden der Klasse verwendet die CRT-Funktionen oder andere Bibliotheksfunktionen verwenden statische Daten (finden Sie unter [potenzielle Fehler übergeben von CRT-Objekten über DLL-Grenzen](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md) Informationen).

- Keine Methoden der Klasse (unabhängig vom inlining) können Typen verwenden, in dem die Instanziierung in der EXE- und DLL statische Datenunterschiede aufweisen.

Sie können vermeiden, Exportieren von Klassen definieren, die eine DLL, die definiert eine Klasse mit virtuellen Funktionen und Funktionen Sie aufrufen kann, instanziieren und Löschen von Objekten des Typs.  Sie können dann virtuelle Funktionen nur für den Typ aufrufen.

C4251 können ignoriert werden, wenn Sie von einem Typ in der C++ Standardbibliothek, die eine Debugversion kompilieren (**/MTd**) und, in dem die Fehlermeldung des Compilers auf _Container_base bezieht.

```cpp
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251
```