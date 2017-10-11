---
title: Compilerwarnung C4355 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4355
dev_langs:
- C++
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 061ad3df17cf9c86fbc5ac98048932aff8b0b25b
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4355"></a>Compilerwarnung C4355
"this": Wird in der Basisliste für den Memberinitialisierer verwendet  
  
 Die **dies** -Zeiger ist nur in nicht statischen Memberfunktionen gültig. Es kann nicht in der Initialisiererliste für eine Basisklasse verwendet werden.  
  
 Konstruktoren für Basisklassen und Member aufgerufen, bevor **dies** Konstruktor. Aktiviert ist, haben Sie einen Zeiger auf ein nicht konstruierter Objekt an einen anderen Konstruktor übergeben. Wenn die anderen Konstruktoren Zugriff auf alle Member oder Memberfunktionen für dieses aufrufen, wird das Ergebnis nicht definiert. Verwenden Sie nicht die **dies** Zeiger, bis die Erstellung abgeschlossen ist.  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Im folgende Beispiel wird C4355 generiert:  
  
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
