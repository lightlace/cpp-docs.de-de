---
title: Compilerfehler C3880
ms.date: 11/04/2016
f1_keywords:
- C3880
helpviewer_keywords:
- C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
ms.openlocfilehash: 0b169309db88291f8a83b6d1192787b6396e84a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338466"
---
# <a name="compiler-error-c3880"></a>Compilerfehler C3880

"Var": Ein literal-Datenmember nicht möglich

Der Typ des eine [literal](../../extensions/literal-cpp-component-extensions.md) -Attribut muss sein, oder während der Kompilierung in einer der folgenden Typen konvertiert werden kann:

- ganzzahligen Typ

- Zeichenfolge

- Enumeration mit einem ganzzahligen oder zugrunde liegenden Typ

Im folgende Beispiel wird die C3880 generiert:

```
// C3880.cpp
// compile with: /clr /c
ref struct Y1 {
   literal System::Decimal staticConst1 = 10;   // C3880
   literal int staticConst2 = 10;   // OK
};
```