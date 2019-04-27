---
title: Schwerwiegender Fehler C1197
ms.date: 11/04/2016
f1_keywords:
- C1197
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
ms.openlocfilehash: e1c00a001c807b0cc6a5946b61ca4e9d5dc0167a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62229120"
---
# <a name="fatal-error-c1197"></a>Schwerwiegender Fehler C1197

'mscorlib.dll_1' kann nicht verwiesen werden, wie das Programm bereits auf 'mscorlib. dll_2' verweist.

Der Compiler ist eine Version der common Language Runtime zugeordnet.  Es wurde jedoch versucht, auf eine Version einer common Language Runtime-Datei von einer früheren Version zu verweisen.

Um diesen Fehler zu beheben, müssen Sie nur verweisen Sie Dateien aus der Version von der common Language Runtime, die geliefert, mit der Version von Visual C++, die Sie Kompilieren mit.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C1197 generiert:

```
// C1197.cpp
// compile with: /clr /c
// processor: x86
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197
// try the following line instead
// #using "mscorlib.dll"
```