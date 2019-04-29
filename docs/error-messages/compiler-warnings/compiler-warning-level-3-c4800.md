---
title: Compilerwarnung (Stufe 4) C4800
ms.date: 03/14/2019
f1_keywords:
- C4800
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
ms.openlocfilehash: 46418063625e16385497740a4f7e3d837e923156
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401552"
---
# <a name="compiler-warning-level-4-c4800"></a>Compilerwarnung (Stufe 4) C4800

::: moniker range=">= vs-2019"
Visual Studio 2019 und höher:
> Implizite Konvertierung von '*Typ*"in" bool ". Möglichen Datenverlust
::: moniker-end

C4800 wird eine Warnung der Stufe 3, in Visual Studio 2015 und früher:
> "*Typ*': erzwingen Wert auf" bool "" True"oder"False"(leistungswarnung)

Diese Warnung wird generiert, wenn ein Wert implizit in den Typ konvertiert wird `bool`. Diese Meldung wird in der Regel durch Zuweisen von verursacht `int` Variablen `bool` Variablen, in denen die `int` Variable enthält nur die Werte **"true"** und **"false"**, werden konnte als Typ neu deklariert `bool`. Wenn Sie den Ausdruck, um Sie verwenden nicht neu schreiben können `bool`, und klicken Sie dann die Sie hinzufügen können "`!=0`" mit dem Ausdruck, der den Ausdruckstyp bietet `bool`. Den Ausdruck in den Typ umwandeln `bool` nicht deaktivieren Sie die Warnung, die beabsichtigt ist.

::: moniker range=">= vs-2017"
Diese Warnung wird in Visual Studio 2017 nicht ausgegeben.
::: moniker-end

::: moniker range=">= vs-2019"
Diese Warnung ist standardmäßig deaktiviert, Visual Studio-2019 ab. Verwendung __/w__*n*__4800__ C4800 als Ebene aktivieren *n* "Warnung" und oder [/Wall](../../build/reference/compiler-option-warning-level.md) um alle Warnungen zu aktivieren, sind standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Compiler Warnings, sind standardmäßig](../../preprocessor/compiler-warnings-that-are-off-by-default.md).
::: moniker-end

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4800 generiert, und es wird gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C4800.cpp
// compile with: /W4 /w44800
int main() {
   int i = 0;

   // To fix, instead try:
   // bool i = 0;

   bool j = i;   // C4800
   j++;
}
```