---
title: unexpected (CRT) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- unexpected
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
apitype: DLLExport
f1_keywords:
- unexpected
dev_langs:
- C++
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
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
ms.openlocfilehash: 7e1188d3cf2136e67d2e212640b2c2c29b7cf1f5
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="unexpected-crt"></a>unexpected (CRT)
Ruft `terminate` oder eine Funktion auf, die Sie mit `set_unexpected` angeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
void unexpected( void );  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `unexpected`-Routine wird nicht mit der aktuellen Implementierung der C++-Ausnahmebehandlung verwendet. `unexpected` ruft standardmäßig `terminate` auf. Sie können dieses Standardverhalten ändern, indem Sie eine benutzerdefinierte Beendigungsfunktion schreiben und mit dem Namen Ihrer Funktion als Argument `set_unexpected` aufrufen. `unexpected` ruft die letzte Funktion auf, die für `set_unexpected` als Argument angegeben wurde.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`unexpected`|\<eh.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)
