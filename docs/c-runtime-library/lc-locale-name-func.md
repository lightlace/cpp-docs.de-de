---
title: ___lc_collate_name_func | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ___lc_locale_name_func
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords:
- ___lc_locale_name_func
dev_langs:
- C++
helpviewer_keywords:
- ___lc_locale_name_func
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 243fcd75c657125e001e4dc0544e9c315df1bd07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="lclocalenamefunc"></a>___lc_locale_name_func
Interne CRT-Funktion. Ruft die aktuellen Gebietsschemanamen des Threads ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
wchar_t** ___lc_locale_name_func(void);  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine Zeichenfolge, die den aktuellen Gebietsschemanamen des Threads enthält.  
  
## <a name="remarks"></a>Hinweise  
 `___lc_locale_name_func` ist eine interne CRT-Funktion, die von anderen CRT-Funktionen verwendet wird, um den aktuellen Gebietsschemanamen aus dem lokalen Threadspeicher für CRT-Daten abzurufen. Diese Information ist auch mit Verwendung der Funktion [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) oder der Funktionen [Setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) verfügbar.  
  
 Interne CRT-Funktionen sind implementierungsspezifisch und mit jedem neuen Release Änderungen unterworfen. Ihre Verwendung in einem Code wird nicht empfohlen.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`___lc_locale_name_func`|crt\src\setlocal.h|  
  
## <a name="see-also"></a>Siehe auch  
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../c-runtime-library/reference/free-locale.md)