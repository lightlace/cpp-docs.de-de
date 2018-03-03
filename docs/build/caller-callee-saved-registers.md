---
title: Gespeicherte Register von Aufrufer Aufgerufenem | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 61e8d57c177ded8102f257cf84adedc0de0e312a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="callercallee-saved-registers"></a>Gespeicherte Register von Aufrufer/Aufgerufenem
Zerstört die Register RAX, RCX, RDX, R8, R9, R10, R11 volatile betrachtet werden und berücksichtigt werden muss Funktionsaufrufe (es sei denn, andernfalls für Sicherheit, provable durch Analyse z. B. Optimierung des ganzen Programms).  
  
 Die Register RBX, RBP, RDI, RSI, RSP, R12, R13, R14 und R15 gelten als nicht flüchtig und müssen gespeichert werden und wiederhergestellt, indem eine Funktion, die verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)