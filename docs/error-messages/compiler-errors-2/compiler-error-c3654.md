---
title: Compilerfehler C3654 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3654
dev_langs: C++
helpviewer_keywords: C3654
ms.assetid: 57d96e3f-6bbb-4eaa-934b-26c23b4ceb2e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e7f96f3e1703c0d43964ba8e5941000e227bde52
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3654"></a>Compilerfehler C3654
'Text': Syntaxfehler in explizites Überschreiben  
  
 Es wurde eine unerwartete Zeichenfolge in einer expliziten Überschreibung. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
 Im folgende Beispiel wird C3654 generiert:  
  
```  
// C3654.cpp  
// compile with: /clr /c  
public ref struct B {  
   virtual void f() = 0;  
   virtual void g() = 0;  
   virtual void h() = 0;  
};  
  
public ref struct Q : B {  
   virtual void f() = B::f, 3 {}   // C3654  
   // try the following line instead  
   // virtual void g() = B::g, B::h {}  
};  
```