---
title: Compilerfehler C3386
ms.date: 11/04/2016
f1_keywords:
- C3386
helpviewer_keywords:
- C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
ms.openlocfilehash: ca78433fcb835ad60b553be28ea746f0f880b315
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743249"
---
# <a name="compiler-error-c3386"></a>Compilerfehler C3386

"Typ": __declspec (dllexport)/\__declspec (dllimport) kann nicht auf einen verwalteten oder winrttype angewendet werden.

Die `dllimport`-und [dllexport](../../cpp/dllexport-dllimport.md) -`__declspec` Modifizierer sind für verwaltete oder Windows-Runtime Typen ungültig.

Im folgenden Beispiel wird C3386 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C3386.cpp
// compile with: /clr /c
ref class __declspec(dllimport) X1 {   // C3386
// try the following line instead
// ref class X1 {
};
```
