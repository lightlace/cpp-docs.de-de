---
title: Compilerfehler C2632
ms.date: 11/04/2016
f1_keywords:
- C2632
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
ms.openlocfilehash: b92d44bcfd04d4de7b39c5bdab5ee146d9b6693b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257633"
---
# <a name="compiler-error-c2632"></a>Compilerfehler C2632

"Typ1", gefolgt von "Typ2" ist unzulässig.

Dieser Fehler kann verursacht werden, wenn es zwischen zwei Typspezifizierern Code vorhanden ist.

Im folgende Beispiel wird die C2632 generiert:

```
// C2632.cpp
int float i;   // C2632
```

Dieser Fehler kann außerdem infolge einer konformitätsverbesserung für Compiler generiert werden, die für Visual Studio .NET 2003 durchgeführt wurde. `bool` ist jetzt ein ordnungsgemäßer Typ. In früheren Versionen `bool` wurde eine Typdefinition, und Sie können Bezeichner erstellen, mit diesem Namen.

Im folgende Beispiel wird die C2632 generiert:

```
// C2632_2.cpp
// compile with: /LD
void f(int bool);   // C2632
```

Benennen Sie den Bezeichner, um diesen Fehler zu beheben, damit der Code in der Visual Studio .NET 2003 und Visual Studio .NET-Versionen von Visual C++ gültig ist.