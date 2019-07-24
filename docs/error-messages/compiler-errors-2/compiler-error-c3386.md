---
title: Compilerfehler C3386
ms.date: 11/04/2016
f1_keywords:
- C3386
helpviewer_keywords:
- C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
ms.openlocfilehash: a9183e1f62e7ebaf5db04a35a45806ec02169e69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328808"
---
# <a name="compiler-error-c3386"></a>Compilerfehler C3386

"Type": "__declspec(dllexport)" "/\__declspec(dllimport) kann nicht auf einen verwalteten oder WinRTtype angewendet werden

Die `dllimport` und [Dllexport](../../cpp/dllexport-dllimport.md) `__declspec` Modifizierer sind nicht zulässig für einen verwalteten oder Windows-Runtime-Typ.

Im folgenden Beispiel wird C3386 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3386.cpp
// compile with: /clr /c
ref class __declspec(dllimport) X1 {   // C3386
// try the following line instead
// ref class X1 {
};
```