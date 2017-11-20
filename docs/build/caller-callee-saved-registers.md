---
title: Gespeicherte Register von Aufrufer Aufgerufenem | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ebdcf30ea56587b71015a04b5e514dd9ff21aeba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="callercallee-saved-registers"></a>Gespeicherte Register von Aufrufer/Aufgerufenem
Zerstört die Register RAX, RCX, RDX, R8, R9, R10, R11 volatile betrachtet werden und berücksichtigt werden muss Funktionsaufrufe (es sei denn, andernfalls für Sicherheit, provable durch Analyse z. B. Optimierung des ganzen Programms).  
  
 Die Register RBX, RBP, RDI, RSI, RSP, R12, R13, R14 und R15 gelten als nicht flüchtig und müssen gespeichert werden und wiederhergestellt, indem eine Funktion, die verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)