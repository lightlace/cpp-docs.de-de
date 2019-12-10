---
title: Compilerwarnung (Stufe 4) C4714
ms.date: 11/04/2016
f1_keywords:
- C4714
helpviewer_keywords:
- C4714
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
ms.openlocfilehash: 8ea4212eaddf14546827728b31299063021a959f
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74989646"
---
# <a name="compiler-warning-level-4-c4714"></a>Compilerwarnung (Stufe 4) C4714

die Funktion "Function" ist als __forceinline nicht Inline gekennzeichnet.

Die angegebene Funktion wurde für die Inline Erweiterung ausgewählt, aber der Compiler hat das Inlining nicht durchgeführt.

Obwohl `__forceinline` eine stärkere Anzeige für den Compiler als `__inline`ist, wird das Inlining nach wie vor im Ermessen des Compilers ausgeführt. es wird jedoch keine Heuristik verwendet, um die Vorteile des Inlining dieser Funktion zu ermitteln.

In einigen Fällen wird der Compiler eine bestimmte Funktion aus mechanischen Gründen nicht Inline Inline. Der Compiler wird z. b. nicht Inline:

- Eine Funktion, wenn dies dazu führen würde, dass SEH C++ und eh gemischt werden.

- Einige Funktionen mit kopierten Kopier Objekten wurden als Wert weitergegeben, wenn-GX/EHs/EHa aktiviert ist.

- Funktionen, die ein nicht windable-Objekt nach Wert zurückgeben, wenn-GX/EHs/EHa auf ON festgelegt ist.

- Funktionen mit der Inlineassembly beim Kompilieren ohne-og/Ox/o1/o2.

- Funktionen mit einer Variablen Argumentliste.

- Eine Funktion mit einer **try** -C++ Anweisung (Ausnahmebehandlung).

Im folgenden Beispiel wird C4714 generiert:

```cpp
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
