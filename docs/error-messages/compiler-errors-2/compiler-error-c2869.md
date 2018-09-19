---
title: Compilerfehler C2869 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2869
dev_langs:
- C++
helpviewer_keywords:
- C2869
ms.assetid: 6e30c001-47f3-4101-b9f1-cc542c9fffae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4a899826ab299665a7a44deaa89416affe5d41f2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101513"
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