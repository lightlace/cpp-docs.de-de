---
title: Compilerwarnung C4355
ms.date: 11/04/2016
f1_keywords:
- C4355
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
ms.openlocfilehash: f1f5e5be2606a03ec5e9ecd0c571f94c25f82494
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623750"
---
# <a name="compiler-warning-c4355"></a>Compilerwarnung C4355

"this": Wird in der Basisliste für den Memberinitialisierer verwendet

Der **this** -Zeiger ist nur in nicht statischen Element Funktionen gültig. Sie kann nicht in der Initialisiererliste für eine Basisklasse verwendet werden.

Die Basisklassenkonstruktoren und Klassenmember-Konstruktoren werden vor **diesem** Konstruktor aufgerufen. Tatsächlich haben Sie einen Zeiger auf ein nicht konstruiertes Objekt an einen anderen Konstruktor übergeben. Wenn diese anderen Konstruktoren auf Member zugreifen oder Element Funktionen aufrufen, ist das Ergebnis nicht definiert. Sie sollten **diesen** Zeiger erst verwenden, wenn alle Konstruktionen abgeschlossen sind.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgenden Beispiel wird C4355 generiert:

```cpp
// C4355.cpp
// compile with: /w14355 /c
#include <tchar.h>

class CDerived;
class CBase {
public:
   CBase(CDerived *derived): m_pDerived(derived) {};
   ~CBase();
   virtual void function() = 0;

   CDerived * m_pDerived;
};

class CDerived : public CBase {
public:
   CDerived() : CBase(this) {};   // C4355 "this" used in derived c'tor
   virtual void function() {};
};

CBase::~CBase() {
   m_pDerived -> function();
}

int main() {
   CDerived myDerived;
}
```