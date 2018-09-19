---
title: Compilerfehler C2815 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2815
dev_langs:
- C++
helpviewer_keywords:
- C2815
ms.assetid: d0256fd6-0721-4c99-b03c-52d96e77a613
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 192c991cfee9fb1925601719ea61c47c5227c753
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057656"
---
# <a name="compiler-error-c2815"></a>Compilerfehler C2815

"Operator delete": der erste formale Parameter muss "" void "*", aber es wurde 'Param' verwendet.

Eine benutzerdefinierte [Delete-Operator](../../standard-library/new-operators.md#op_delete) Funktion muss ein erste formale Parameter des Typs akzeptieren `void *`.

Im folgende Beispiel wird die C2815 generiert:

```
// C2815.cpp
// compile with: /c
class CMyClass {
public:
   void mf1(int *a);
   void operator delete(CMyClass *);   // C2815
   void operator delete(void *);
};
```