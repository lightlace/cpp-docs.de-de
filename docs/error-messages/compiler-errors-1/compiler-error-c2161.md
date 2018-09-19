---
title: Compilerfehler C2161 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2161
dev_langs:
- C++
helpviewer_keywords:
- C2161
ms.assetid: d6798821-13bb-4e60-924f-85f7bf955387
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac32776c954974f0f2f81789c6e78de894786b73
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051820"
---
# <a name="compiler-error-c2161"></a>Compilerfehler C2161

"##" kann nicht am Ende einer Makrodefinition stehen

Eine Makrodefinition endete mit einem tokeneinfügenden Operator (##).

Im folgenden Beispiel wird C2161 generiert:

```
// C2161.cpp
// compile with: /c
#define mac(a,b) a   // OK
#define mac(a,b) a##   // C2161
```