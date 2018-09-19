---
title: Compilerwarnung (Stufe 2) C4309 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4309
dev_langs:
- C++
helpviewer_keywords:
- C4309
ms.assetid: cb3f41ef-fd8a-4def-baa1-924e751fca68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b7eba833b547a54adc0644303ab51d3852740a8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041973"
---
# <a name="compiler-warning-level-2-c4309"></a>Compilerwarnung (Stufe 2) C4309

'Konvertierung': Verkürzung eines konstanten Wertes

Die typkonvertierung bewirkt, dass eine Konstante, die für dieses Volume zugewiesene Speicherplatz überschreiten. Sie müssen möglicherweise einen größeren Typ für die Konstante verwenden.

Im folgende Beispiel wird die C4309 generiert:

```
// C4309.cpp
// compile with: /W2
int main()
{
   char c = 128;   // C4309
}
```