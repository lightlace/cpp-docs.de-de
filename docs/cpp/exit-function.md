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
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 240636bf7b6f10421c5d4ebd202a5fb3473a819d
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

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
