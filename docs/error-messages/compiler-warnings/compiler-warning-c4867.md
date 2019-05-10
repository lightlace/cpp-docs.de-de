---
title: Compilerwarnung C4867
ms.date: 11/04/2016
f1_keywords:
- C4867
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
ms.openlocfilehash: 0fd5de46f713aed08508f8755c9e54c3ff46366b
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447205"
---
# <a name="compiler-warning-c4867"></a>Compilerwarnung C4867

'Funktion': Funktionsaufruf fehlt die Argumentliste. Verwenden Sie 'Aufruf', um einen Zeiger auf Member zu erstellen

Ein Zeiger auf Member-Funktion wurde nicht ordnungsgemäß initialisiert.

Diese Warnung kann generiert werden, infolge einer konformitätsverbesserung für Compiler, die für Visual Studio 2005 durchgeführt wurde: verbesserte Pointer-to-Member-Konformität.  Code, der vor Visual Studio 2005 kompiliert wird nun C4867 generiert.

Diese Warnmeldung wird immer als Fehler ausgegeben. Verwenden Sie das [warning](../../preprocessor/warning.md) -Pragma, um diese Warnung zu deaktivieren. Weitere Informationen über C4867 und MFC/ATL finden Sie unter [_ATL_ENABLE_PTM_WARNING](../../atl/reference/compiler-options-macros.md#_atl_enable_ptm_warning).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4867 generiert.

```
// C4867.cpp
// compile with: /c
class A {
public:
   void f(int) {}

   typedef void (A::*TAmtd)(int);

   struct B {
      TAmtd p;
   };

   void g() {
      B b = {f};   // C4867
      B b2 = {&A::f};   // OK
   }
};
```