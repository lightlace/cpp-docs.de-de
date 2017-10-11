---
title: Compiler-Fehler C2776 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2776
dev_langs:
- C++
helpviewer_keywords:
- C2776
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5642335519263c3b191d1c14399f3d00f366a8c9
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2776"></a>Compiler-Fehler C2776 generiert
nur eine "get"-Methode kann pro Eigenschaft angegeben werden  
  
 Nur eine angeben `get` -Funktion in der [Eigenschaft](../../cpp/property-cpp.md) erweiterten Attribute. Dieser Fehler tritt auf, wenn mehrere `get` Funktionen angegeben werden.  
  
 Im folgende Beispiel wird C2776 generiert:  
  
```  
// C2776.cpp  
struct A {  
   __declspec(property(get=GetProp,get=GetPropToo))  
   // try the following line instead  
   // __declspec(property(get=GetProp))  
      int prop;   // C2776  
   int GetProp(void);  
   int GetPropToo(void);  
};  
```
