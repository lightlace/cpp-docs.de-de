---
title: _findclose | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _findclose
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _findclose
- findclose
dev_langs: C++
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4747592dbda7a903d5d8a50cebde9ef006ec765d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="findclose"></a>_findclose
Schließt das angegebene Suchhandle und gibt zugeordnete Ressourcen frei.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _findclose(   
   intptr_t handle   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `handle`  
 Das Suchhandle, das von einem vorherigen Aufruf von `_findfirst` zurückgegeben wird.  
  
## <a name="return-value"></a>Rückgabewert  
 `_findclose` gibt bei Erfolg 0 zurück. Hingegen gibt-1 zurück und legt `errno` zu `ENOENT`, gibt an, dass keine übereinstimmenden Dateien gefunden werden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_findclose`|\<io.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Systemaufrufe](../../c-runtime-library/system-calls.md)   
 [Dateinamen-Suchfunktionen](../../c-runtime-library/filename-search-functions.md)