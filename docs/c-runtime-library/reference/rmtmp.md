---
title: _rmtmp | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _rmtmp
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- rmtmp
- _rmtmp
dev_langs: C++
helpviewer_keywords:
- removing temporary files
- _rmtmp function
- files [C++], temporary
- rmtmp function
- files [C++], removing
- temporary files [C++], removing
ms.assetid: 7419501e-2587-4f2a-b469-0dca07f84736
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 79103471b09815b2ca4a99c2e9c22ed5af512ef4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="rmtmp"></a>_rmtmp
Löscht temporäre Dateien.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
int _rmtmp( void );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 `_rmtmp` gibt die Anzahl der geschlossenen und gelöschten temporären Dateien zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_rmtmp`-Funktion bereinigt alle temporären Dateien im aktuellen Verzeichnis. Die Funktion entfernt nur die Dateien, die von `tmpfile` erstellt wurden; verwenden Sie sie nur in dem Verzeichnis, in dem die temporären Dateien erstellt wurden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_rmtmp`|\<stdio.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [tmpfile](../../c-runtime-library/reference/tmpfile.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)