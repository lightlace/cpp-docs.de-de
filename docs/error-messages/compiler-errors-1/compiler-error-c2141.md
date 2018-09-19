---
title: Compilerfehler C2141 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2141
dev_langs:
- C++
helpviewer_keywords:
- C2141
ms.assetid: 10cf770f-0500-4220-ac90-a863b7ea5fe6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e657c82f1f98547e7b8db337430a3ac635b320b2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088149"
---
# <a name="compiler-error-c2141"></a>Compilerfehler C2141

arraygrößenüberlauf

Ein Array überschreitet den Grenzwert von 2GB. Reduzieren Sie die Größe des Arrays.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2141 generiert.

```
// C2141.cpp
// processor: IPF
class A {
   short m_n;
};

int main()
{
   A* pA = (A*)(-1);
   pA = new A[0x8000000000000001];   // C2141

   A* pA2 = (A*)(-1);
   pA2 = new A[0x80000000000000F];   // OK
}
```