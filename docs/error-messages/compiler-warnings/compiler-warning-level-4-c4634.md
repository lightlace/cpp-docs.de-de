---
title: Compilerwarnung (Stufe 4) C4634
ms.date: 11/04/2016
f1_keywords:
- C4634
helpviewer_keywords:
- C4634
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
ms.openlocfilehash: 7d0e2af13128a201d96aa905d85621e14441a673
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408211"
---
# <a name="compiler-warning-level-4-c4634"></a>Compilerwarnung (Stufe 4) C4634

XML-Dokumentkommentar: Kann nicht angewendet werden: Grund

XML-Dokumentationstags können nicht auf alle C++-Konstrukte angewendet werden.  So kann z. B. einem Namespace oder einer Vorlage kein Dokumentationskommentar hinzugefügt werden.

Weitere Informationen finden Sie unter [XML Documentation](../../build/reference/xml-documentation-visual-cpp.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4634 generiert.

```
// C4634.cpp
// compile with: /W4 /doc /c
/// This is a namespace.   // C4634
namespace hello {
   class MyClass  {};
};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4634 generiert.

```
// C4634_b.cpp
// compile with: /W4 /doc /c
/// This is a template.   // C4634
template <class T>
class MyClass  {};
```