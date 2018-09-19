---
title: Compilerfehler C2383 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2383
dev_langs:
- C++
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c529c22636f112291fa53b852899cad78dac589
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113226"
---
# <a name="compiler-error-c2383"></a>Compilerfehler C2383

"*Symbol*': Standardargumente dürfen nicht auf dieses Symbol

Der C++-Compiler lässt die Standardargumente für Zeiger auf Funktionen nicht.

Dieser Code wurde vom Visual C++-Compiler in Versionen vor Visual Studio 2005 akzeptiert, jetzt jedoch einen Fehler. Weisen Sie für Code, der in allen Versionen von Visual C++ funktioniert einen Standardwert nicht auf ein Zeiger auf Funktion-Argument.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C2383 generiert und gezeigt, eine mögliche Lösung:

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```