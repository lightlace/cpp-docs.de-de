---
title: Compilerwarnung (Stufe 4) C4625
ms.date: 11/04/2016
f1_keywords:
- C4625
helpviewer_keywords:
- C4625
ms.assetid: 4cc99e50-846c-4784-97da-48b977067851
ms.openlocfilehash: edcb43bf11c073e6ce721ba999fd99d28a8df15d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62220493"
---
# <a name="compiler-warning-level-4-c4625"></a>Compilerwarnung (Stufe 4) C4625

'derived class': Der Kopierkonstruktor wurde implizit als gelöscht definiert, da ein Basisklassen-Kopierkonstruktor nicht zugreifbar ist oder gelöscht wurde.

Ein Kopieroperator wurde gelöscht, oder es kann nicht auf diesen in einer Basisklasse zugegriffen werden. Daher wurde er nicht für eine abgeleitete Klasse generiert. Bei jedem Versuch, ein Objekt dieses Typs zu kopieren, wird ein Compilerfehler generiert.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4625 generiert und gezeigt, wie Sie diesen Fehler beheben.

```
// C4625.cpp
// compile with: /W4 /c
#pragma warning(default : 4625)

struct A {
   A() {}

private:
   A(const A&) {}
};

struct C : private virtual A {};
struct B :  C {};   // C4625 no copy constructor

struct D : A {};
struct E :  D {};   // OK
```