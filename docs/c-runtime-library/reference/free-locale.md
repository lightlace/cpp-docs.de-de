---
title: _free_locale | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _free_locale
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
- __free_locale
- free_locale
- _free_locale
dev_langs: C++
helpviewer_keywords:
- __free_locale function
- free_locale function
- locales, freeing
- _free_locale function
ms.assetid: 1f08d348-ab32-4028-a145-6cbd51b49af9
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dda92ec24c310900eafa7aca5ec401788ed1552d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="freelocale"></a>_free_locale
Gibt ein locale-Objekt frei  
  
## <a name="syntax"></a>Syntax  
  
```  
void _free_locale(  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `locale`  
 Das freizugebende locale-Objekt  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_free_locale` dient zum Freigeben des locale-Objektes, das über einen Aufruf `_get_current_locale` oder `_create_locale` abgerufen wird.  
  
 Der vorherige Name dieser Funktion, `__free_locale` (mit zwei führenden Unterstrichen), ist veraltet.  
  
## <a name="requirements"></a>Anforderungen  
  
|`Routine`|Erforderlicher Header|  
|---------------|---------------------|  
|`_free_locale`|\<locale.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [_get_current_locale](../../c-runtime-library/reference/get-current-locale.md)   
 [_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)