---
title: Compilerwarnung C4355 | Microsoft Docs
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
ms.openlocfilehash: 13f57b8a7c279b820f4f9fc4a68715804a12e625
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273805"
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