---
title: Compiler-Fehler C2776 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2776
dev_langs:
- C++
helpviewer_keywords:
- C2776
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: afbf3c48e5445d101408c2539cc077071b639044
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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