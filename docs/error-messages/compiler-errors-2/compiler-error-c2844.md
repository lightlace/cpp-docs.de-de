---
title: Compilerfehler C2844 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2844
dev_langs:
- C++
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 45e0a7eb7a8846d90cc8e0743f5484ba1b58208a
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2844"></a>Compilerfehler C2844
'Member': ein Member der Schnittstelle "Schnittstelle" nicht möglich  
  
 Ein [Schnittstellenklasse](../../windows/interface-class-cpp-component-extensions.md) darf keine Datenmember enthalten, es sei denn, sie auch eine Eigenschaft ist.  
  
 Etwas anderes als eine Eigenschaft oder der Member-Funktion ist in einer Schnittstelle nicht zulässig. Darüber hinaus sind die Konstruktoren, Destruktoren und Operatoren nicht zulässig.  
  
 Im folgende Beispiel wird C2844 generiert:  
  
```  
// C2844a.cpp  
// compile with: /clr /c  
public interface class IFace {  
   int i;   // C2844  
   // try the following line instead  
   // property int Size;  
};  
```  

