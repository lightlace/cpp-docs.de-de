---
title: Compilerwarnung (Stufe 3) C4637
ms.date: 11/04/2016
f1_keywords:
- C4637
helpviewer_keywords:
- C4637
ms.assetid: 5fd347c1-2de9-408f-9136-1bf1ff273622
ms.openlocfilehash: 80c55494a391922453f2d89ae26ee5f47dc433b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401695"
---
# <a name="compiler-warning-level-3-c4637"></a>Compilerwarnung (Stufe 3) C4637

XML-dokumentkommentarziel: \<enthalten >-Tag wurde verworfen.  reason

Die Syntax einer [ \<enthalten >](../../build/reference/include-visual-cpp.md) -Tags war nicht richtig.

Im folgenden Beispiel wird C4637 generiert:

```
// C4637.cpp
// compile with: /clr /doc /LD /W3
using namespace System;

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <include file="c:\davedata\jtest\xml_include.doc"/>
   // Try the following line instead:
   // /// <include file='xml_include.doc' path='MyDocs/MyMembers/*' />
   void MyMethod() {
   }
};   // C4637
```