---
title: _local_unwind2 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _local_unwind2
apilocation:
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- _local_unwind2
- local_unwind2
dev_langs:
- C++
helpviewer_keywords:
- _local_unwind2 function
- local_unwind2 function
ms.assetid: 44f1fa82-e01e-490f-a6e6-18fc6811c28c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5bee1decf5b5a3676e6111960282c19e87628c48
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="localunwind2"></a>_local_unwind2
Interne CRT-Funktion. Führt alle Beendigungshandler aus, die in der angegebenen Bereichtabelle aufgelistet sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
void _local_unwind2(  
   PEXCEPTION_REGISTRATION xr,  
   int stop  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `xr`  
 Ein Registrierungseintrag, der mit einer Bereichtabelle verbunden ist.  
  
 [in] `stop`  
 Die lexikalische Ebene, die darauf hinweist, wo `_local_unwind2` aufhören sollte.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird nur von der Laufzeitumgebung verwendet. Rufen Sie die Methode nicht in Ihrem Code auf.  
  
 Wenn diese Methode Beendigungshandler ausführt, beginnt sie an der aktuellen lexikalischen Ebene und arbeitet sich die lexikalischen Ebenen hoch, bis sie die Ebene erreicht, die von `stop` angegeben wird. Sie führt keine Beendigungshandler auf der Ebene aus, die von `stop` angegeben ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)