---
title: Compilerfehler C3469
ms.date: 11/04/2016
f1_keywords:
- C3469
helpviewer_keywords:
- C3469
ms.assetid: e23b0e5c-c704-4e67-a868-bf02c2055d85
ms.openlocfilehash: 546de5a65f6e4c2fd370ba781d01945df2bbfce5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760542"
---
# <a name="compiler-error-c3469"></a>Compilerfehler C3469

'typ': Eine generische Klasse kann nicht weitergeleitet werden.

Typweiterleitung kann nicht für generische Klassen verwendet werden.

Weitere Informationen finden Sie unter [TypweiterleitungC++(/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine Komponente erstellt:

```cpp
// C3469.cpp
// compile with: /clr /LD
generic<typename T>
public ref class GR {};

public ref class GR2 {};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3466 generiert:

```cpp
// C3469_b.cpp
// compile with: /clr /c
#using "C3469.dll"
[assembly:TypeForwardedTo(GR::typeid)];   // C3469
[assembly:TypeForwardedTo(GR2::typeid)];   // OK
```
