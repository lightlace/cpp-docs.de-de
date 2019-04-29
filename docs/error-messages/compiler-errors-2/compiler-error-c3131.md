---
title: Compilerfehler C3131
ms.date: 11/04/2016
f1_keywords:
- C3131
helpviewer_keywords:
- C3131
ms.assetid: 38f20fac-83c9-4cd9-b7b5-74ca8f650ea6
ms.openlocfilehash: 082839c01a2da4b0d149962367b9719932d2b272
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349931"
---
# <a name="compiler-error-c3131"></a>Compilerfehler C3131

Projekt muss ein "Modulattribut" mit der Eigenschaft "Name" aufweisen.

Die [Modul](../../windows/module-cpp.md) Attribut muss einen Name-Parameter aufweisen.

Im folgende Beispiel wird die C3131 generiert:

```
// C3131.cpp
[emitidl];
[module];   // C3131
// try the following line instead
// [module (name="MyLib")];

[public]
typedef long int LongInt;
```