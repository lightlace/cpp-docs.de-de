---
title: _get_terminate | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_terminate
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_terminate
- _get_terminate
- __get_terminate
dev_langs: C++
helpviewer_keywords:
- __get_terminate function
- get_terminate function
- _get_terminate function
ms.assetid: c8f168c4-0ad5-4832-a522-dd1ef383c208
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 87f0bc967175bd339d8e421d72de8a4f7d369631
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="getterminate"></a>_get_terminate
Gibt die Beendigungsroutine durch den Aufruf von `terminate` zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
terminate_function _get_terminate( void );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die Funktion zurück, die durch [Set_terminate](../../c-runtime-library/reference/set-terminate-crt.md) registriert wurde. Wenn keine Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherzustellen. Dieser Wert kann NULL sein.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_get_terminate`|\<eh.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)