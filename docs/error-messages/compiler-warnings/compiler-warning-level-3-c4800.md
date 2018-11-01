---
title: Compilerwarnung (Stufe 3) C4800
ms.date: 11/04/2016
f1_keywords:
- C4800
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
ms.openlocfilehash: 591b706249201691c7a9743d2cad082eb61e68b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636136"
---
# <a name="compiler-warning-level-3-c4800"></a>Compilerwarnung (Stufe 3) C4800

> "*Typ*': erzwingen Wert auf" bool "" True"oder"False"(leistungswarnung)

Diese Warnung wird generiert, wenn ein Wert, der nicht `bool` zugewiesen oder in den Typ umgewandelt `bool`. Diese Meldung wird in der Regel durch Zuweisen von verursacht `int` Variablen `bool` Variablen, in denen die `int` Variable enthält nur die Werte **"true"** und **"false"**, werden konnte als Typ neu deklariert `bool`. Wenn Sie den Ausdruck, um Sie verwenden nicht neu schreiben können `bool`, und klicken Sie dann die Sie hinzufügen können "`!=0`" mit dem Ausdruck, der den Ausdruckstyp bietet `bool`. Den Ausdruck in den Typ umwandeln `bool` deaktiviert nicht die Warnung, die beabsichtigt ist.

Diese Warnung wird in Visual Studio 2017 nicht mehr generiert.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4800 generiert, und es wird gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C4800.cpp
// compile with: /W3
int main() {
   int i = 0;

   // To fix, instead try:
   // bool i = 0;

   bool j = i;   // C4800
   j++;
}
```