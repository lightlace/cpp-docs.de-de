---
title: Compilerfehler C2755 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2755
dev_langs:
- C++
helpviewer_keywords:
- C2755
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56ecf997df2aeb1a41b5021d61b24073e871b55f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064905"
---
# <a name="compiler-error-c2755"></a>Compilerfehler C2755

"Param": Nichttyp-Parameter einer teilweisen Spezialisierung muss ein einfacher Bezeichner

Der Nichttyp-Parameter muss ein einfacher Kennzeichner, etwas zu sein, die der Compiler zur Kompilierzeit in einen einzelnen Bezeichner oder ein konstanter Wert nicht beheben kann.

Im folgende Beispiel wird die C2755 generiert:

```
// C2755.cpp
template<int I, int J>
struct A {};

template<int I>
struct A<I,I*5> {};   // C2755
// try the following line instead
// struct A<I,5> {};
```