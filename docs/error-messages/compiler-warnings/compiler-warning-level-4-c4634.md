---
title: Compilerwarnung (Stufe 4) C4634
ms.date: 11/04/2016
f1_keywords:
- C4634
helpviewer_keywords:
- C4634
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
ms.openlocfilehash: a26356dd32f1513eadf4ef2b82175cf71aed13a4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536668"
---
# <a name="compiler-warning-level-4-c4634"></a>Compilerwarnung (Stufe 4) C4634

XML-Dokumentkommentar: Kann nicht angewendet werden: Grund

XML-Dokumentationstags können nicht auf alle C++-Konstrukte angewendet werden.  So kann z. B. einem Namespace oder einer Vorlage kein Dokumentationskommentar hinzugefügt werden.

Weitere Informationen finden Sie unter [XML Documentation](../../ide/xml-documentation-visual-cpp.md).

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