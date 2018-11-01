---
title: Compilerwarnung C4355
ms.date: 11/04/2016
f1_keywords:
- C4355
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
ms.openlocfilehash: 6b74c8dd5ce9860cb218d21790f12ba05e9be22f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554171"
---
# <a name="compiler-warning-c4355"></a>Compilerwarnung C4355

"this": Wird in der Basisliste für den Memberinitialisierer verwendet

Die **dies** Zeiger nur innerhalb nicht statischer Memberfunktionen gültig ist. Es kann nicht in der Initialisierungsliste für Basisklasse verwendet werden.

Die Basis-Klasse, Konstruktoren und Klassenmember werden aufgerufen, bevor **dies** Konstruktor. Aktiviert ist, haben Sie ein Zeiger auf ein nicht erstellten Objekt an einen anderen Konstruktor übergeben. Wenn die anderen Konstruktoren den Zugriff auf alle Member oder Memberfunktionen dazu aufrufen, wird das Ergebnis nicht definiert sein. Verwenden Sie nicht die **dies** Zeiger, bis die Erstellung abgeschlossen ist.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgende Beispiel wird die C4355 generiert:

```
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