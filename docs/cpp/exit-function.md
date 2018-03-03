---
title: Exit-Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee6a34a70465904e6725f42e68eb4a00c03a1661
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="exit-function"></a>exit-Funktion
Die **beenden** -Funktion, in der standardincludedatei deklariert \<stdlib.h >, beendet ein C++-Programm.  
  
 Der Wert, der als Argument angegeben **beenden** an das Betriebssystem als Rückgabecode oder Exitcode: die Anwendung zurückgegeben wird. Gemäß der Konvention bedeutet ein Rückgabecode von Null, dass das Programm erfolgreich abgeschlossen wurde.  
  
> [!NOTE]
>  Sie können die Konstanten `EXIT_FAILURE` und `EXIT_SUCCESS`, definiert in \<stdlib.h >, um den Erfolg oder Fehler des Programms anzeigt.  
  
 Ausgeben einer `return` -Anweisung aus der **main** Funktion entspricht dem Aufrufen der **beenden** Funktion, bei dem Rückgabewert als Argument.  
  
 Weitere Informationen finden Sie unter [beenden](../c-runtime-library/reference/exit-exit-exit.md) in der *Run-Time Library Reference*.  
  
## <a name="see-also"></a>Siehe auch  
 [Programmbeendigung](../cpp/program-termination.md)