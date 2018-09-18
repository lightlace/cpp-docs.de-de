---
title: Compilerfehler C2756 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2756
dev_langs:
- C++
helpviewer_keywords:
- C2756
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 252f212f9034151bc5e77d1d2d6e64e1ee388faa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061213"
---
# <a name="compiler-error-c2756"></a>Compilerfehler C2756

'template type': Bei einer teilweisen Spezialisierung sind Standardvorlagenargumente nicht zulässig

Die Vorlage für eine teilweise Spezialisierung darf kein Standardargument enthalten.

Im folgenden Beispiel wird C2756 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C2756.cpp
template <class T>
struct S {};

template <class T=int>
// try the following line instead
// template <class T>
struct S<T*> {};   // C2756
```