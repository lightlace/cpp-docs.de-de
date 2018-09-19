---
title: Compilerfehler C2766 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2766
dev_langs:
- C++
helpviewer_keywords:
- C2766
ms.assetid: 8032f4ca-6827-4f04-9c61-c44643c85cc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee59a8ebc0de3c539d1c9b775dcf06525b1a77fa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051528"
---
# <a name="compiler-error-c2766"></a>Compilerfehler C2766

explizite Spezialisierung; "Spezialisierung" wurde bereits definiert.

Doppelte explizite spezialisierungen sind nicht zulässig. Weitere Informationen finden Sie unter [explizite Spezialisierung von Funktionsvorlagen](../../cpp/explicit-specialization-of-function-templates.md).

Im folgende Beispiel wird die C2766 generiert:

```
// C2766.cpp
// compile with: /c
template<class T>
struct A {};

template<>
struct A<int> {};

template<>
struct A<int> {};   // C2766
// try the following line instead
// struct A<char> {};
```