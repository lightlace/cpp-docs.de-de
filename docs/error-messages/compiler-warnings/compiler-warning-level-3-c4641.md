---
title: Compilerwarnung (Stufe 3) C4641
ms.date: 11/04/2016
f1_keywords:
- C4641
helpviewer_keywords:
- C4641
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
ms.openlocfilehash: 9357088106a45026eae543f8627ea59988e73995
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401669"
---
# <a name="compiler-warning-level-3-c4641"></a>Compilerwarnung (Stufe 3) C4641

XML-Dokumentkommentar enthält einen mehrdeutigen Querverweis

Der Compiler konnte einen Verweis eindeutig zu beheben. Um diese Warnung zu beheben, geben Sie die erforderlichen Parameterinformationen für den Verweis eindeutig zu machen.

Weitere Informationen finden Sie unter [XML Documentation](../../build/reference/xml-documentation-visual-cpp.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4641 generiert.

```
// C4641.cpp
// compile with: /W3 /doc /clr /c

/// <see cref="f" />   // C4641
// try the following line instead
// /// <see cref="f(int)" />
public ref class GR {
public:
   void f( int ) {}
   void f( char ) {}
};
```