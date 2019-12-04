---
title: Compilerfehler C3747
ms.date: 11/04/2016
f1_keywords:
- C3747
helpviewer_keywords:
- C3747
ms.assetid: a9a4be67-5d9c-4dcc-9ae9-baae46cbecde
ms.openlocfilehash: 761bb44f5097d998fd885fdb1c5caacf90db3642
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761867"
---
# <a name="compiler-error-c3747"></a>Compilerfehler C3747

fehlender standardtypparameter: Parameter Parameter

Generische Parameter oder Vorlagen Parameter mit Standardwerten können nicht in der Parameterliste von Parametern befolgt werden, die keine Standardwerte aufweisen.

Im folgenden Beispiel wird C3747 generiert:

```cpp
// C3747.cpp
template <class T1 = int, class T2>   // C3747
struct MyStruct {};
```

Mögliche Lösung:

```cpp
// C3747b.cpp
// compile with: /c
template <class T1, class T2 = int>
struct MyStruct {};
```
