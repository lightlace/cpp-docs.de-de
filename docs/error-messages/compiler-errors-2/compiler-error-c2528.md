---
title: Compilerfehler C2528 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2528
dev_langs:
- C++
helpviewer_keywords:
- C2528
ms.assetid: 2ea9d583-67a8-4b16-b35f-a50eeffc03c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c588457743c601e31c24fd0a53de652477fbf05
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072601"
---
# <a name="compiler-error-c2528"></a>Compilerfehler C2528

'Name': Zeiger auf Verweis ist nicht zulässig

Sie können einen Zeiger auf einen Verweis nicht deklarieren. Die Variable vor dem Deklarieren eines Zeigers auf die es zu dereferenzieren.

Im folgende Beispiel wird die C2528 generiert:

```
// C2528.cpp
int i;
int &ir = i;
int & (*irptr) = ir;    // C2528
```