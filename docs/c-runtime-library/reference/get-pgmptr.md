---
title: _get_pgmptr | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_pgmptr
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
- get_pgmptr
- _get_pgmptr
dev_langs: C++
helpviewer_keywords:
- get_pgmptr function
- _get_pgmptr function
- pgmptr global variable
- _pgmptr global variable
ms.assetid: 29f16a9f-a685-4721-add3-7fad4f67eece
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 962d6198a9daeeca0a79a814da11d1d60438d18f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="getpgmptr"></a>_get_pgmptr
Ruft den aktuellen Wert der globalen `_pgmptr`-Variable ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _get_pgmptr(   
   char **pValue   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `pValue`  
 Ein Zeiger für eine Zeichenfolge, die mit dem aktuellen Wert der `_pgmptr`-Variable ausgefüllt wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt 0 (null) zurück, wenn der Vorgang erfolgreich war. Wenn ein Fehler auftritt, erscheint ein Fehlercode. Wenn `pValue` `NULL` ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `EINVAL` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_pgmptr` (globale Variable) enthält den vollständigen Pfad zur ausführbaren Datei, die dem Prozess zugeordnet. Weitere Informationen finden Sie unter [_pgmptr, _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_get_pgmptr`|\<stdlib.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [_get_wpgmptr](../../c-runtime-library/reference/get-wpgmptr.md)