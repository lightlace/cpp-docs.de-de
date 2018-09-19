---
title: Compilerfehler C3212 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3212
dev_langs:
- C++
helpviewer_keywords:
- C3212
ms.assetid: 9e271bb6-a51f-4b96-b26b-9f4ca28fca0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f860d2368deb0a7d3946c2d3feabb70b88de1083
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096014"
---
# <a name="compiler-error-c3212"></a>Compilerfehler C3212

"specialization": Eine explizite Spezialisierung eines Vorlagenmembers muss ein Member einer expliziten Spezialisierung sein

Eine explizite Spezialisierung wurde falsch formatiert.

Im folgenden Beispiel wird C3212 generiert:

```
// C3212.cpp
// compile with: /LD
template <class T>
struct S {
   template <class T1>
   struct S1;
};

template <class T>   // C3212
template <>
struct S<T>::S1<int> {};

/*
// try the following instead
template <>
template <>
struct S<int>::S1<int> {};
*/

/*
// or, the following
template <>
struct S<int> {
   template <class T1>
   struct S1;
};

template <>
struct S<int>::S1<int> {
};
*/
```