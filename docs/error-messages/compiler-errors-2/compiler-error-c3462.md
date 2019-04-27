---
title: Compilerfehler C3462
ms.date: 11/04/2016
f1_keywords:
- C3462
helpviewer_keywords:
- C3462
ms.assetid: 56b75f35-9fad-42d9-a969-eeca5d709bec
ms.openlocfilehash: 020556be73f0bad8bea6836c9ec0dd0b92dd7f39
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222370"
---
# <a name="compiler-error-c3462"></a>Compilerfehler C3462

"Typ": Nur ein importierter Typ kann weitergeleitet werden.

Das TypeForwardedTo-Attribut muss auf einen Typ in den Metadaten angewendet werden, auf die verwiesen wird.

Weitere Informationen finden Sie unter [Typweiterleitung (C++ / CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine Komponente erstellt:

```
// C3462.cpp
// compile with: /clr /LD
public ref class R {};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3462 generiert:

```
// C3462b.cpp
// compile with: /clr /c
#using "C3462.dll"
ref class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3462
[assembly:TypeForwardedTo(R::typeid)];
```