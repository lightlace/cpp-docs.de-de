---
title: Compilerfehler C2756
ms.date: 11/04/2016
f1_keywords:
- C2756
helpviewer_keywords:
- C2756
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
ms.openlocfilehash: ccbbb7875fdae48fd00f87f9a63f3764c143daae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442834"
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