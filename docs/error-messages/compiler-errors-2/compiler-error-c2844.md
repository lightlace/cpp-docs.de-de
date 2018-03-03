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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3353a6dbacaca2779bb4feffe55958baf0c944e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
