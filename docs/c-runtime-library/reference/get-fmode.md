---
title: _get_fmode | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_fmode
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
- get_fmode
- _get_fmode
dev_langs:
- C++
helpviewer_keywords:
- _get_fmode function
- file translation [C++], default mode
- get_fmode function
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
caps.latest.revision: 19
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
ms.openlocfilehash: 3081981cde81b200d5896bab4d362db13742eb42
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="getfmode"></a>_get_fmode
Ruft den Standarddateiübersetzungsmodus für Datei E/A-Vorgänge auf.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _get_fmode(   
   int * pmode   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `pmode`  
 Ein Zeiger auf eine ganze Zahl, die durch den aktuellen Standardmodus ersetzt werden soll: `_O_TEXT` oder `_O_BINARY`.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt 0 (null) zurück, wenn der Vorgang erfolgreich war. Wenn ein Fehler auftritt, erscheint ein Fehlercode. Wenn `pmode` `NULL` ist, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `EINVAL` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion legt die globale Variable [_fmode](../../c-runtime-library/fmode.md) fest. Diese Variable gibt den Standard-Dateiübersetzungsmodus für Datei-E/A-Vorgänge auf niedriger Ebene und Stream-Datei-E/A-Vorgänge an, wie z.B. `_open`, `_pipe`, `fopen` und `freopen`.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_get_fmode`|\<stdlib.h>|\<fcntl.h >|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel in [_set_fmode](../../c-runtime-library/reference/set-fmode.md).  
  
## <a name="see-also"></a>Siehe auch  
 [_fmode](../../c-runtime-library/fmode.md)   
 [_set_fmode](../../c-runtime-library/reference/set-fmode.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [Text- und Binärmodusdatei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md)
