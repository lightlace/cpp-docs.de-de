---
title: _get_printf_count_output | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_printf_count_output
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
- get_printf_count_output
- _get_printf_count_output
dev_langs:
- C++
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 4373fc075e46110cbcef411b283b8566bf74508c
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="getprintfcountoutput"></a>_get_printf_count_output
Gibt an, ob [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)-Familienfunktionen das `%n`-Format unterstützen.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _get_printf_count_output();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ungleich null, wenn `%n` unterstützt wird; 0, wenn `%n` nicht unterstützt wird.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `%n` nicht unterstützt wird (Standard), wird der ungültige Parameterhandler aufgerufen, indem `%n` in der Formatzeichenfolge auf eine der `printf` Funktionen trifft, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn `%n` -Unterstützung aktiviert ist (finden Sie unter [_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md)) dann `%n` verhält sich wie beschrieben in [Syntax der Formatangabe: printf- und Wprintf-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_get_printf_count_output`|\<stdio.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md).  
  
## <a name="see-also"></a>Siehe auch  
[_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md)  

