---
title: Signalkonstanten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SIGTERM
- SIGFPE
- SIGABRT
- SIGILL
- SIGINT
- SIGSEGV
dev_langs:
- C++
helpviewer_keywords:
- SIGTERM constant
- SIGABRT constant
- SIGSEGV constant
- SIGFPE constant
- SIGINT constant
- signal constants
- SIGILL constant
ms.assetid: a3b39281-dae7-4e44-8d68-e6a610c669dd
caps.latest.revision: 11
author: corob-msft
ms.author: corob
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 511d700aa5eaa47c59648160e152cfc14c4c1177
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="signal-constants"></a>Signalkonstanten
## <a name="syntax"></a>Syntax  
  
```  
#include <signal.h>  
```  
  
## <a name="remarks"></a>Hinweise  
 Das `sig`-Argument muss eine der unten aufgelisteten (und in SIGNAL.H definierten) Manifestkonstanten sein.  
  
 `SIGABRT`  
 Nicht ordnungsgemäße Beendigung. Die Standardaktion beendet das aufrufende Programm mit Exitcode 3.  
  
 `SIGABRT_COMPAT`  
 Identisch mit SIGABRT. Zur Kompatibilität mit anderen Plattformen.  
  
 `SIGFPE`  
 Gleitkommafehler, z.B. Überlauf, Division durch 0 (null) oder eine ungültige Operation. Die Standardaktion beendet das aufrufende Programm.  
  
 `SIGILL`  
 Ungültige Anweisung. Die Standardaktion beendet das aufrufende Programm.  
  
 `SIGINT`  
 STRG+C-Unterbrechung. Die Standardaktion beendet das aufrufende Programm mit Exitcode 3.  
  
 `SIGSEGV`  
 Ungültiger Speicherzugriff. Die Standardaktion beendet das aufrufende Programm.  
  
 `SIGTERM`  
 An das Programm gesendete Beendigungsanforderung. Die Standardaktion beendet das aufrufende Programm mit Exitcode 3.  
  
 `SIG_ERR`  
 Ein Rückgabetyp aus einem Signal, der angibt, das ein Fehler aufgetreten ist.  
  
## <a name="see-also"></a>Siehe auch  
 [signal](../c-runtime-library/reference/signal.md)   
 [__raise](../c-runtime-library/reference/raise.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)
