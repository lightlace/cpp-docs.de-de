---
title: Compilerwarnung (Stufe 4) C4714
ms.date: 11/04/2016
f1_keywords:
- C4714
helpviewer_keywords:
- C4714
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
ms.openlocfilehash: ed94e5b716a697ec96d7fecac75433823c9a67e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395182"
---
# <a name="compiler-warning-level-4-c4714"></a>Compilerwarnung (Stufe 4) C4714

'Funktion' als __forceinline markierte nicht inline

Die angegebene Funktion für die Inlineerweiterung ausgewählt wurde, aber der Compiler hat nicht ausgeführt, das inlining.

Obwohl `__forceinline` stärker an den Compiler als `__inline`, inlining erfolgt immer noch nach Ermessen des Compilers, jedoch keine Heuristik werden verwendet, um zu bestimmen, die Vorteile von inlining dieser Funktion.

In einigen Fällen der Compiler werden nicht Inline eine bestimmte Funktion technischen Gründen. Beispielsweise führt der Compiler nicht Inline Folgendes aus:

- Eine Funktion, wenn es in das Kombinieren von sowohl SEH und C++-EH führen würde.

- Einige Funktionen für die Kopie erstellt Objekte, die als Wert übergeben wird, wenn - GX/EHs/EHa aktiviert ist.

- Funktionen, die ein entladbarer Objekt nach Wert zurückgeben, wenn - GX/EHs/EHa aktiviert ist.

- Funktioniert mit Inlineassembly beim Kompilieren ohne - Og/Ox/O1/O2.

- Funktioniert mit der eine Variable Argumentliste.

- Eine Funktion mit einem **versuchen** -Anweisung (C++-Ausnahmebehandlung).

Im folgende Beispiel wird die C4714 generiert:

```
// C4714.cpp
// compile with: /Ob1 /GX /W4
__forceinline void func1()
{
   try
   {
   }
   catch (...)
   {
   }
}

void func2()
{
   func1();   // C4714
}

int main()
{
}
```