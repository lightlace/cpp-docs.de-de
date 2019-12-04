---
title: Compilerfehler C3462
ms.date: 11/04/2016
f1_keywords:
- C3462
helpviewer_keywords:
- C3462
ms.assetid: 56b75f35-9fad-42d9-a969-eeca5d709bec
ms.openlocfilehash: 56227f124d49630d8776f291ada302bd6cd6e983
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756603"
---
# <a name="compiler-error-c3462"></a>Compilerfehler C3462

"Typ": Nur ein importierter Typ kann weitergeleitet werden.

Das TypeForwardedTo-Attribut muss auf einen Typ in den Metadaten angewendet werden, auf die verwiesen wird.

Weitere Informationen finden Sie unter [TypweiterleitungC++(/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine Komponente erstellt:

```cpp
// C3462.cpp
// compile with: /clr /LD
public ref class R {};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3462 generiert:

```cpp
// C3462b.cpp
// compile with: /clr /c
#using "C3462.dll"
ref class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3462
[assembly:TypeForwardedTo(R::typeid)];
```
