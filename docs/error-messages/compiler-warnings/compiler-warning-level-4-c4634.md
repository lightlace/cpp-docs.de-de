---
title: Compilerwarnung (Stufe 4) C4634 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4634
dev_langs:
- C++
helpviewer_keywords:
- C4634
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4fe89eaffda80ab40efedc4facf75929d07a7537
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034914"
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