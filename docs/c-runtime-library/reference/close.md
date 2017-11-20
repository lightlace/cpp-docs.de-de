---
title: _close | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _close
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
- _close
dev_langs:
- C++
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
caps.latest.revision: 12
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 9dab323afc6c70e81592119e0cec2775c239d87f
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="close"></a>_close
Schließt eine Datei.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _close(   
   int fd   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `fd`  
 Dateideskriptor, der auf die geöffnete Datei verweist.  
  
## <a name="return-value"></a>Rückgabewert  
 `_close` gibt 0 zurück, wenn die Datei erfolgreich geschlossen wurde. Ein Rückgabewert von – 1 zeigt einen Fehler.  
  
## <a name="remarks"></a>Hinweise  
 Die `_close`-Funktion schließt die mit `fd` verknüpfte Datei.  
  
 Der Dateideskriptor und das zugrunde liegende Betriebssystem-Dateihandle werden geschlossen. Daher ist es nicht notwendig, `CloseHandle` aufzurufen, wenn die Datei ursprünglich mithilfe der Win32-Funktion `CreateFile` geöffnet und mit `_open_osfhandle` in einen Dateideskriptor umgewandelt wurde.  
  
 Diese Funktion überprüft ihre Parameter. Wenn `fd` ein fehlerhafter Dateideskriptor ist, wird – wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben – der Handler für ungültige Parameter aufgerufen. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion -1 zurück, und `errno` wird auf `EBADF` gesetzt.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_close`|\<io.h>|\<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [_open](../../c-runtime-library/reference/open-wopen.md).  
  
## <a name="see-also"></a>Siehe auch  
 [E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_unlink, _wunlink](../../c-runtime-library/reference/unlink-wunlink.md)