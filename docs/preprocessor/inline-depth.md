---
title: Inline_depth | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
dev_langs: C++
helpviewer_keywords:
- pragmas, inline_depth
- inline_depth pragma
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f105512910658603139105ecf1cf1d5b7030ad00
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="inlinedepth"></a>inline_depth
Gibt die heuristische Inlinesuchtiefe an, sodass keine Funktion "inline" ist, wenn die Tiefe im Aufrufdiagramm größer als `n` ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma inline_depth( [n] )  
```  
  
## <a name="remarks"></a>Hinweise  
 Dieses Pragma steuert das inlining von Funktionen, die als [Inline](../cpp/inline-functions-cpp.md) und [__inline](../cpp/inline-functions-cpp.md) oder Inlining automatisch unter der/Ob2-Option.  
  
 `n` kann ein Wert zwischen 0 und 255 sein, wobei 255 unendliche Tiefe im Aufrufdiagramm bedeutet, und NULL die Inlineerweiterung unterdrückt.  Wenn `n` nicht angegeben ist, wird der Standardwert (254) verwendet.  
  
 Die **Inline_depth** Pragma legt fest, wie oft eine Serie von Funktionsaufrufen erweitert werden kann. Wenn die Inlinetiefe z. B. vier ist und A B aufruft und B dann C, werden alle drei Aufrufe inline erweitert. Wenn jedoch die nächste Inlineerweiterung zwei ist, werden nur A und B erweitert, und C bleibt als Funktionsaufruf bestehen.  
  
 Um dieses Pragma verwenden zu können, müssen Sie die /Ob-Compilerfunktion auf 1 oder 2 festlegen. Die bei der Verwendung dieses Pragma festgelegte Tiefe ist beim ersten Funktionsaufruf nach dem Pragma wirksam.  
  
 Die Inlinetiefe kann während der Erweiterung verringert, aber nicht erhöht werden. Wenn die inlinetiefe sechs ist und während der Erweiterung der Präprozessor erkennt eine **Inline_depth** bleibt von Pragma mit einem Wert von acht, die Tiefe sechs.  
  
 Die **Inline_depth** Pragma wirkt sich nicht auf Funktionen, die mit markierten `__forceinline`.  
  
> [!NOTE]
>  Rekursive Funktionen können inline in einer maximalen Tiefe von 16 Aufrufen ersetzt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline_recursion](../preprocessor/inline-recursion.md)