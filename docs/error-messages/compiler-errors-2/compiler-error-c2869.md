---
title: Compilerfehler C2869
ms.date: 11/04/2016
f1_keywords:
- C2869
helpviewer_keywords:
- C2869
ms.assetid: 6e30c001-47f3-4101-b9f1-cc542c9fffae
ms.openlocfilehash: 38ac73484814e0089b412938ffc2776872deff3e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614447"
---
# <a name="compiler-error-c2869"></a>Compilerfehler C2869

'Name': wurde bereits als Namespace definiert

Sie können ein Name wird bereits verwendet wird, wie ein Namespace nicht wiederverwenden.

Im folgende Beispiel wird die C2869 generiert:

```
// C2869.cpp
// compile with: /c
namespace A { int i; };

class A {};   // C2869, A is already used
```