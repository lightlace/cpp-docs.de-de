---
title: ___lc_codepage_func | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ___lc_codepage_func
apilocation:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
- msvcr110.dll
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- lc_codepage_func
- ___lc_codepage_func
dev_langs:
- C++
helpviewer_keywords:
- ___lc_codepage_func
ms.assetid: 6a663bd0-5a63-4a2f-9507-872ec1582aae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8532984c8557b095753c0e8cf30b6e63d8b01ce0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="lccodepagefunc"></a>___lc_codepage_func
Interne CRT-Funktion. Ruft die aktuelle Codepage des Threads ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
UINT ___lc_codepage_func(void);  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Die aktuelle Codepage des Threads.  
  
## <a name="remarks"></a>Hinweise  
 `___lc_codepage_func` ist eine interne CRT-Funktion, die von anderen CRT-Funktionen verwendet wird, um die aktuelle Codepage aus dem lokalen Threadspeicher für CRT-Daten abzurufen. Diese Information kann auch durch Verwendung der [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)-Funktion gewonnen werden.  
  
 Eine *Codepage* ist eine Zuordnung von Einzelbyte- oder Doppelbytecodes zu einzelnen Zeichen. Zu verschiedenen Codepages gehören verschiedene spezielle Zeichen, die normalerweise für eine Sprache oder eine Gruppe von Sprachen angepasst sind. Weitere Informationen zu Codepages finden Sie unter [Code Pages](../c-runtime-library/code-pages.md).  
  
 Interne CRT-Funktionen sind implementierungsspezifisch und mit jedem neuen Release Änderungen unterworfen. Ihre Verwendung in einem Code wird nicht empfohlen.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`___lc_codepage_func`|crt\src\setlocal.h|  
  
## <a name="see-also"></a>Siehe auch  
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../c-runtime-library/reference/free-locale.md)