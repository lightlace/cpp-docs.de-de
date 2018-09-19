---
title: Compilerfehler C3412 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3412
dev_langs:
- C++
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6a04de132c85cb09a960d3a0edfcb3b07127119
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054572"
---
# <a name="compiler-error-c3412"></a>Compilerfehler C3412

'Template': die Vorlage im aktuellen Bereich kann nicht spezialisiert

Eine Vorlage kann nicht im Gültigkeitsbereich der Klasse, sondern nur im globalen oder im Namespace-Gültigkeitsbereich spezialisiert werden.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3412 generiert.

```
// C3412.cpp
template <class T>
struct S {
   template <>
   struct S<int> {};   // C3412 in a class
};
```

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine mögliche Lösung.

```
// C3412b.cpp
// compile with: /c
template <class T>
struct S {};

template <>
struct S<int> {};
```