---
title: Schwerwiegender Fehler C1197
ms.date: 11/04/2016
f1_keywords:
- C1197
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
ms.openlocfilehash: 7f698262c73f0b311a92a8940107b552430919bb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747240"
---
# <a name="fatal-error-c1197"></a>Schwerwiegender Fehler C1197

auf ' mscorlib. dll_1 ' kann nicht verwiesen werden, weil das Programm bereits auf ' mscorlib. dll_2 ' verwiesen hat.

Der Compiler wird mit einer Version der Common Language Runtime abgeglichen.  Es wurde jedoch versucht, auf eine Version einer Common Language Runtime Datei von einer früheren Version zu verweisen.

Sie können diesen Fehler beheben, indem Sie nur auf Dateien aus der Version des Common Language Runtime verweisen, die mit der C++ Version von Visual ausgeliefert wurde, mit der Sie kompilieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C1197 generiert:

```cpp
// C1197.cpp
// compile with: /clr /c
// processor: x86
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197
// try the following line instead
// #using "mscorlib.dll"
```
