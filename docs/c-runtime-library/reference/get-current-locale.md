---
title: _get_current_locale | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_current_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_current_locale
- __get_current_locale
- _get_current_locale
dev_langs:
- C++
helpviewer_keywords:
- get_current_locale function
- _get_current_locale function
- locales, getting information on
- __get_current_locale function
ms.assetid: 572217f2-a37a-4105-a293-a250b4fabd99
caps.latest.revision: 13
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: e2f14ad541750967d63a50c13ec82a9ed57fce05
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="getcurrentlocale"></a>_get_current_locale
Ruft ein Gebietsschemaobjekt auf, das das aktuelle Gebietsschema darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
_locale_t _get_current_locale(void);  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Gebietsschemaobjekt, das das aktuelle Gebietsschema darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die `_get_current_locale` Funktion ruft die aktuell festgelegten Gebietsschema des Threads und gibt ein Locale-Objekt, das diesem Gebietsschema darstellt.  
  
 Der vorherige Name dieser Funktion, `__get_current_locale` (mit zwei führenden Unterstrichen), ist veraltet.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_get_current_locale`|\<locale.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../../c-runtime-library/reference/free-locale.md)
