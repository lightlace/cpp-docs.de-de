---
title: Schwerwiegender Fehler C1197 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1197
dev_langs:
- C++
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 58561e7bd906fc750779ef53a4f68ec27088a3b7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024761"
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