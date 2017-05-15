---
title: _query_new_handler | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _query_new_handler
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _query_new_handler
- query_new_handler
dev_langs:
- C++
helpviewer_keywords:
- query_new_handler function
- handler routines
- error handling
- _query_new_handler function
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
caps.latest.revision: 10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 63d43e80009b0d6c8f2d827f6ea5b239d7a39663
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="querynewhandler"></a>_query_new_handler
Gibt die Adresse der aktuellen neuen Handlerroutine zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
_PNH _query_new_handler(  
   void   
);  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die Adresse der aktuellen neuen Handlerroutine zurück, wie in `_set_new_handler` festgelegt.  
  
## <a name="remarks"></a>Hinweise  
 Die C++ `_query_new_handler`-Funktion gibt die Adresse der aktuellen Ausnahmebehandlungsfunktion zurück, die von der [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md)-C++-Funktion festgelegt wurde. `_set_new_handler` wird verwendet, um eine Funktion für die Ausnahmebehandlung anzugeben, die die Steuerung übernehmen wird, wenn der **new**-Operator keinen Arbeitsspeicher zuordnen kann. Weitere Informationen finden Sie unter der Erläuterung [new and delete operators (Operatoren new und delete)](../../cpp/new-and-delete-operators.md) in der C++-Sprachreferenz.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_query_new_handler`|\<new.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)
