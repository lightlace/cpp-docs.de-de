---
title: Compilerwarnung (Stufe 2) C4275
ms.date: 11/04/2016
f1_keywords:
- C4275
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
ms.openlocfilehash: 985a622e2c89306c453ae6c860d21e6265d0fff1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594323"
---
# <a name="compiler-warning-level-2-c4275"></a>Compilerwarnung (Stufe 2) C4275

nicht - DLL-Schnittstelle Classkey 'Bezeichner' als Basisklasse verwendet für DLL-Schnittstelle Classkey "Bezeichner"

Eine exportierte Klasse wurde von einer Klasse abgeleitet, die nicht exportiert wurde.

Um das Risiko einer datenbeschädigung zu minimieren, beim Exportieren einer Klasse mit [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), sicher, dass:

- Alle statischen Daten erfolgt über Funktionen, die aus der DLL exportiert werden.

- Keine Inline-Methoden der Klasse können statische Daten ändern.

- Keine Inline-Methoden der Klasse verwendet die CRT-Funktionen oder andere Bibliotheksfunktionen verwenden statische Daten.

- Keine Inline Klassenfunktionen verwenden Sie CRT-Funktionen oder anderen Bibliotheksfunktionen zur, z. B. greifen Sie auf statische Daten.

- Keine Methoden der Klasse (unabhängig vom inlining) können Typen verwenden, in dem die Instanziierung in der EXE- und DLL statische Datenunterschiede aufweisen.

Sie können vermeiden, Exportieren von Klassen definieren, die eine DLL, die definiert eine Klasse mit virtuellen Funktionen und Funktionen Sie aufrufen kann, instanziieren und Löschen von Objekten des Typs.  Sie können dann virtuelle Funktionen nur für den Typ aufrufen.

C4275 können in Visual C++ ignoriert werden, wenn Sie von einem Typ in der C++-Standardbibliothek, die eine Debugversion kompilieren (**/MTd**) und, in dem die Fehlermeldung des Compilers auf _Container_base bezieht.

```
// C4275.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275
```