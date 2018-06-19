---
title: Signalaktionskonstanten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- SIG_IGN
- SIG_DFL
dev_langs:
- C++
helpviewer_keywords:
- signal action constants
- SIG_IGN constant
- SIG_DFL constant
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b6f645d474e697bf662a5dd63973dd54c329eb9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409435"
---
# <a name="signal-action-constants"></a>Signalaktionskonstanten
Die Aktion, die unabhängig des Werts von `func` ausgeführt wird, wenn das Interruptsignal empfangen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <signal.h>  
```  
  
## <a name="remarks"></a>Hinweise  
 Das `func`-Argument muss entweder eine Funktionsadresse oder eine der unten aufgelisteten und in SIGNAL.H definierten Manifestkonstanten sein.  
  
 `SIG_DFL`  
 Systemstandardantwort wird verwendet. Wenn das aufrufende Programm Datenstrom-E/A verwendet, werden von der Laufzeitbibliothek erstellte Puffer nicht geleert.  
  
 `SIG_IGN`  
 Ignoriert das Interruptsignal. Dieser Wert sollte nie `SIGFPE` zugewiesen werden, da der Gleitkommazustand des Prozesses undefiniert bleibt.  
  
 `SIG_SGE`  
 Zeigt an, dass ein Fehler in dem Signal aufgetreten ist.  
  
 `SIG_ACK`  
 Gibt an, dass eine Bestätigung empfangen wurde.  
  
 `SIG_ERR`  
 Ein Rückgabetyp aus einem Signal, der angibt, das ein Fehler aufgetreten ist.  
  
## <a name="see-also"></a>Siehe auch  
 [signal](../c-runtime-library/reference/signal.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)