---
title: Inline_depth | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
dev_langs:
- C++
helpviewer_keywords:
- pragmas, inline_depth
- inline_depth pragma
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e40b9382abc8ee0fa0c003964eebe75bc075e473
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849872"
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