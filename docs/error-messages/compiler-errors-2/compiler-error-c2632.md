---
title: Compilerfehler C2632 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2632
dev_langs:
- C++
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7bf03c35c60bebb52c94ed04cca2349f35c06fbc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093649"
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