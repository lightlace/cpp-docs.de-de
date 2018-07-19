---
title: Exit-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d08ac1375fa383543eaafb5b3ce49cd2bbfbc4da
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941079"
---
# <a name="exit-function"></a>exit-Funktion
Die `exit` -Funktion, in der standardincludedatei deklariert \<stdlib.h >, beendet ein C++-Programm.  
  
 Der als Argument bereitgestellte Wert `exit` an das Betriebssystem als des Programms Rückgabecode oder Exitcode zurückgegeben wird. Gemäß der Konvention bedeutet ein Rückgabecode von Null, dass das Programm erfolgreich abgeschlossen wurde.  
  
> [!NOTE]
>  Sie können die Konstanten EXIT_FAILURE und EXIT_SUCCESS, definiert \<stdlib.h >, um den Erfolg oder Fehler des Programms anzugeben.  
  
 Ausgeben einer **zurückgeben** -Anweisung aus der `main` Funktion entspricht dem Aufrufen der `exit` Funktion mit dem Rückgabewert als Argument.  
  
 Weitere Informationen finden Sie unter [beenden](../c-runtime-library/reference/exit-exit-exit.md) in die *Run-Time Library Reference*.  
  
## <a name="see-also"></a>Siehe auch  
 [Programmbeendigung](../cpp/program-termination.md)