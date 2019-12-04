---
title: Compilerfehler C2756
ms.date: 11/04/2016
f1_keywords:
- C2756
helpviewer_keywords:
- C2756
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
ms.openlocfilehash: f9b3ea261db825f00004a2f447636c15d2d0d52e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759541"
---
# <a name="compiler-error-c2756"></a>Compilerfehler C2756

'template type': Bei einer teilweisen Spezialisierung sind Standardvorlagenargumente nicht zulässig

Die Vorlage für eine teilweise Spezialisierung darf kein Standardargument enthalten.

Im folgenden Beispiel wird C2756 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C2756.cpp
template <class T>
struct S {};

template <class T=int>
// try the following line instead
// template <class T>
struct S<T*> {};   // C2756
```
