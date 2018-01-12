---
title: Exit-Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Exit
dev_langs: C++
helpviewer_keywords: exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b9e0d6a7f903d4af39698b2d98c005cbf64515eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="exit-function"></a>exit-Funktion
Die **beenden** -Funktion, in der standardincludedatei STDLIB deklariert. H, beendet ein C++-Programm.  
  
 Der Wert, der als Argument angegeben **beenden** an das Betriebssystem als Rückgabecode oder Exitcode: die Anwendung zurückgegeben wird. Gemäß der Konvention bedeutet ein Rückgabecode von Null, dass das Programm erfolgreich abgeschlossen wurde.  
  
> [!NOTE]
>  Sie können die Konstanten `EXIT_FAILURE` und `EXIT_SUCCESS` verwenden, die in STDLIB.H definiert sind, um den Erfolg oder den Fehler des Programms anzugeben.  
  
 Ausgeben einer `return` -Anweisung aus der **main** Funktion entspricht dem Aufrufen der **beenden** Funktion, bei dem Rückgabewert als Argument.  
  
 Weitere Informationen finden Sie unter [beenden](../c-runtime-library/reference/exit-exit-exit.md) in der *Run-Time Library Reference*.  
  
## <a name="see-also"></a>Siehe auch  
 [Programmbeendigung](../cpp/program-termination.md)