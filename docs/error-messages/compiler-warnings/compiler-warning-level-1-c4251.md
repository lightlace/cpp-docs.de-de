---
title: Compilerwarnung (Stufe 1) C4251 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4251
dev_langs:
- C++
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d964c375adf80caef3bb5a6eb06c67ef8e3e7200
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890048"
---
# <a name="compiler-warning-level-1-c4251"></a>Compilerwarnung (Stufe 1) C4251

'Bezeichner': Klasse 'Typ' Dll-Schnittstelle, von der Klasse "Typ2" verwendet werden muss

Um das Risiko einer datenbeschädigung zu minimieren, beim Exportieren einer Klasse mit [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), sicher, dass:

- Alle statischen Daten ist der Zugriff über Funktionen, die aus der DLL exportiert werden.

- Keine Inline-Methoden der Klasse können statische Daten ändern.

- Keine Inline-Methoden der Klasse verwendet die CRT-Funktionen oder andere Bibliotheksfunktionen verwenden statische Daten (finden Sie unter [potenzielle Fehler übergeben von CRT-Objekten über DLL-Grenzen](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md) Informationen).

- Keine Methoden der Klasse (unabhängig vom inlining) können Typen verwenden, in dem die Instanziierung in der EXE- und DLL statische Datenunterschiede aufweisen.

Sie können vermeiden, Exportieren von Klassen definieren, die eine DLL, die definiert eine Klasse mit virtuellen Funktionen und Funktionen Sie aufrufen kann, instanziieren und Löschen von Objekten des Typs.  Sie können dann virtuelle Funktionen nur für den Typ aufrufen.

C4251 können ignoriert werden, wenn Sie von einem Typ in der C++-Standardbibliothek, die eine Debugversion kompilieren (**/MTd**) und, in dem die Fehlermeldung des Compilers auf _Container_base bezieht.

```cpp
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251
```