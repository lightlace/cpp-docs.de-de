---
title: Compilerwarnung C4355 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4355
dev_langs:
- C++
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 44833c8e640002f2f94d44938641fa3c1fa33db7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115306"
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