---
title: spawn-Konstanten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _P_NOWAIT
- _P_OVERLAY
- _P_WAIT
- _P_DETACH
- _P_NOWAITO
dev_langs: C++
helpviewer_keywords:
- _P_OVERLAY constant
- P_DETACH constant
- P_OVERLAY constant
- P_NOWAIT constant
- _P_DETACH constant
- _P_NOWAIT constant
- _P_NOWAITO constant
- P_NOWAITO constant
- spawn constants
- P_WAIT constant
- _P_WAIT constant
ms.assetid: e0533e88-d362-46fc-b53c-5f193226d879
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8f5f30cbf6598e4ac8d88652a6a842dcd6209273
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="spawn-constants"></a>spawn-Konstanten
## <a name="syntax"></a>Syntax  
  
```  
#include <process.h>  
```  
  
## <a name="remarks"></a>Hinweise  
 Das `mode`-Argument bestimmt, welche Aktion durch den aufrufenden Prozess vor und während eines spawn-Vorgangs durchgeführt wird. Die folgenden Werte für `mode` sind möglich:  
  
|Konstante|Bedeutung|  
|--------------|-------------|  
|`_P_OVERLAY`|Überlagert einen aufrufenden Prozess mit einem neuen Prozess, wobei der aufrufende Prozess vernichtet wird (gleiche Auswirkung wie `_exec`-Aufrufe).|  
|`_P_WAIT`|Hält einen aufrufenden Thread bis zum Abschluss der Ausführung des neuen Prozesses an (synchrones `_spawn`).|  
|`_P_NOWAIT`, `_P_NOWAITO`|Setzt die Ausführung eines aufrufenden Prozesses gleichzeitig mit dem neuen Prozess fort (asynchrones `_spawn`).|  
|`_P_DETACH`|Setzt die Ausführung des aufrufenden Prozesses fort; der neue Prozess wird im Hintergrund ohne Zugriff auf Konsole oder Tastatur ausgeführt. Bei Aufrufen von `_cwait` für den neuen Prozess tritt ein Fehler auf. Dies ist ein asynchrones `_spawn`.|  
  
## <a name="see-also"></a>Siehe auch  
 [_spawn, _wspawn-Funktionen](../c-runtime-library/spawn-wspawn-functions.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)