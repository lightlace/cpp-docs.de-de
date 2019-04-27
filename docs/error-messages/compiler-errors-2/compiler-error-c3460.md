---
title: Compilerfehler C3460
ms.date: 11/04/2016
f1_keywords:
- C3460
helpviewer_keywords:
- C3460
ms.assetid: adbf8775-10ca-4654-acdf-58dd765351cd
ms.openlocfilehash: 9ffbc5102855574aba668a2c501cd08dbaebe5b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222357"
---
# <a name="compiler-error-c3460"></a>Compilerfehler C3460

'type': Nur ein benutzerdefinierter Typ kann weitergeleitet werden.

Weitere Informationen finden Sie unter [Typweiterleitung (C++ / CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine Komponente erstellt:

```
// C3460.cpp
// compile with: /LD /clr
public ref class R {};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3460 generiert:

```
// C3460_b.cpp
// compile with: /clr /c
#using "C3460.dll"
[assembly:TypeForwardedTo(int::typeid)];   // C3460
[assembly:TypeForwardedTo(R::typeid)];
```