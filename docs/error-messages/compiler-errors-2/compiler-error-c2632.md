---
title: Compilerfehler C2632
ms.date: 11/04/2016
f1_keywords:
- C2632
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
ms.openlocfilehash: f69d43bf50f5f13957e49d1e9ffa798a3db5a7b3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754692"
---
# <a name="compiler-error-c2632"></a>Compilerfehler C2632

"Typ1" gefolgt von "Typ2" ist unzulässig.

Dieser Fehler kann verursacht werden, wenn ein Code zwischen zwei typspezifibezeichmern fehlt.

Im folgenden Beispiel wird C2632 generiert:

```cpp
// C2632.cpp
int float i;   // C2632
```

Dieser Fehler kann auch infolge einer compilerübereinstimmungs-Arbeit generiert werden, die für Visual Studio .NET 2003 durchgeführt wurde. `bool` ist nun ein geeigneter Typ. In früheren Versionen war `bool` eine typedef, und Sie konnten Bezeichner mit diesem Namen erstellen.

Im folgenden Beispiel wird C2632 generiert:

```cpp
// C2632_2.cpp
// compile with: /LD
void f(int bool);   // C2632
```

Benennen Sie den Bezeichner um, damit der Code in den Visual Studio .NET 2003-und Visual Studio .NET-Versionen von C++Visual Studio gültig ist.
