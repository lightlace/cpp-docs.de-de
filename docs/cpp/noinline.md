---
title: Noinline | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: noinline_cpp
dev_langs: C++
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6b8548f428509c2af45858e1baf927da54ebe8f6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="noinline"></a>noinline
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 **__declspec(noinline)** teilt dem Compiler mit nie Inline eine bestimmten Member-Funktion (Funktion in einer Klasse).  
  
 Es lohnt sich möglicherweise, eine Funktion nicht inline auszuführen, wenn die Funktion klein und für die Leistung des Codes nicht wichtig ist. Das ist der Fall, wenn die Funktion klein ist und wahrscheinlich nicht häufig aufgerufen wird, z. B. eine Funktion, die eine Fehlerbedingung behandelt.  
  
 Beachten Sie Folgendes: Wenn eine Funktion als `noinline` markiert ist, ist die aufrufende Funktion kleiner und somit selbst ein Kandidat für Compiler-Inlining.  
  
```  
class X {  
   __declspec(noinline) int mbrfunc() {  
      return 0;   
   }   // will not inline  
};  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [inline, __inline, \__forceinline](inline-functions-cpp.md)

