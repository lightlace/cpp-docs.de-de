---
title: Signalaktionskonstanten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SIG_IGN
- SIG_DFL
dev_langs: C++
helpviewer_keywords:
- signal action constants
- SIG_IGN constant
- SIG_DFL constant
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 26a5b349836b7c9b08a66d4df8f3d2bedbe5b63f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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