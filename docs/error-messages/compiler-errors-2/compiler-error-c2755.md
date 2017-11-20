---
title: Compiler-Fehler C2755 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2755
dev_langs:
- C++
helpviewer_keywords:
- C2755
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 56889ff193d057104c25b31bea8029e9426a9bbc
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2755"></a>Compiler-Fehler C2755 generiert
'Param': Nichttyp-Parameter einer teilweisen Spezialisierung muss ein einfacher Bezeichner  
  
 Der Nichttyp-Parameter muss ein einfacher Bezeichner, etwas sein, die der Compiler zur Kompilierzeit einen einzelnen Bezeichner oder ein konstanter Wert auflösen kann.  
  
 Im folgende Beispiel wird C2755 generiert:  
  
```  
// C2755.cpp  
template<int I, int J>  
struct A {};  
  
template<int I>   
struct A<I,I*5> {};   // C2755  
// try the following line instead  
// struct A<I,5> {};  
```