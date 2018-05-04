---
title: Gespeicherte Register von Aufrufer Aufgerufenem | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f65e88c8609d6a2097e9e54c3f52cbd27dce36d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="callercallee-saved-registers"></a>Gespeicherte Register von Aufrufer/Aufgerufenem
Zerstört die Register RAX, RCX, RDX, R8, R9, R10, R11 volatile betrachtet werden und berücksichtigt werden muss Funktionsaufrufe (es sei denn, andernfalls für Sicherheit, provable durch Analyse z. B. Optimierung des ganzen Programms).  
  
 Die Register RBX, RBP, RDI, RSI, RSP, R12, R13, R14 und R15 gelten als nicht flüchtig und müssen gespeichert werden und wiederhergestellt, indem eine Funktion, die verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)