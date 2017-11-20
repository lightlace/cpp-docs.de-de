---
title: Compilerfehler C3670 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3670
dev_langs:
- C++
helpviewer_keywords:
- C3670
ms.assetid: d0fa9c6e-8f90-48c7-9066-31b4fa5942eb
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 773ee85df3e19245b665521be8d65055ffe3bf17
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3670"></a>Compilerfehler C3670
"override": kann nicht Basisklasse kann nicht zugegriffen werden, Methode "-Schnittstellenmethode überschreiben  
  
 Eine Außerkraftsetzung kann nur auf eine Funktion stattfinden, deren Zugriffsebene in einem abgeleiteten Typ verfügbar macht. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
 Im folgende Beispiel wird C3670 generiert:  
  
```  
// C3670.cpp  
// compile with: /clr /c  
public ref class C {  
// Uncomment the following line to resolve.  
// public:  
   virtual void g() { }  
};  
  
public ref class D : public C {  
public:  
   virtual void f() new sealed = C::g {};   // C3670  
};  
```