---
title: Compilerwarnung (Stufe 1) C4377 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4377
dev_langs:
- C++
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 613ebe183b61c6b9894ed3b726f90061e2b24ef6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047173"
---
# <a name="compiler-warning-level-1-c4377"></a>Compilerwarnung (Stufe 1) C4377

systemeigene Typen sind standardmäßig privat. -d1PrivateNativeTypes ist veraltet.

In früheren Versionen waren systemeigene Typen in Assemblys öffentliche standardmäßig und einer internen, nicht dokumentierten-Compileroption (**/d1PrivateNativeTypes**) wurde verwendet, um diese als privat kennzeichnen.

Alle Typen, systemeigen und CLR sind jetzt standardmäßig in einer Assembly, private damit **/d1PrivateNativeTypes** wird nicht mehr benötigt.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4377 generiert.

```
// C4377.cpp
// compile with: /clr /d1PrivateNativeTypes /W1
// C4377 warning expected
int main() {}
```