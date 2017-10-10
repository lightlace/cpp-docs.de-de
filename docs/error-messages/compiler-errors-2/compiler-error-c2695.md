---
title: Compiler-Fehler C2695 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2695
dev_langs:
- C++
helpviewer_keywords:
- C2695
ms.assetid: 3f6f2091-c38b-40ea-ab6c-f1846f5702d7
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1ae253ade1093d447616a39e788a80b843290f6a
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2695"></a>Compiler-Fehler C2695 generiert
"Funktion1": Überschreiben der virtuellen Funktion unterscheidet sich von "Funktion2" nur durch die Aufrufkonvention  
  
 Die Signatur einer Funktion in einer abgeleiteten Klasse kann keine Funktion in einer Basisklasse zu überschreiben und ändern die Aufrufkonvention.  
  
 Im folgende Beispiel wird C2695 generiert:  
  
```  
// C2695.cpp  
class C {  
   virtual void __fastcall func();  
};  
  
class D : public C {  
   virtual void __clrcall func();   // C2695  
};  
```
