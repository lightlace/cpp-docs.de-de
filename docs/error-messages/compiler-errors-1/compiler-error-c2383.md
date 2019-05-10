---
title: Compilerfehler C2383
ms.date: 11/04/2016
f1_keywords:
- C2383
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
ms.openlocfilehash: e9c1774fe7cd4a6883aa79f384cc64521a57ed17
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448006"
---
# <a name="compiler-error-c2383"></a>Compilerfehler C2383

"*Symbol*': Standardargumente dürfen nicht auf dieses Symbol

Der C++-Compiler lässt die Standardargumente für Zeiger auf Funktionen nicht.

Dieser Code wurde vom Microsoft akzeptiert C++ -Compiler in Versionen vor Visual Studio 2005 jetzt jedoch einen Fehler. Weisen Sie für Code, der in allen Versionen von Visual C++ funktioniert einen Standardwert nicht auf ein Zeiger auf Funktion-Argument.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C2383 generiert und gezeigt, eine mögliche Lösung:

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```